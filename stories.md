---
layout: default
title: Engineering Stories
description: Detailed technical narratives behind the systems, failures, and design decisions.
permalink: /stories/
---

<div class="section-header">
  <h2>Engineering Stories</h2>
  <span class="section-tag">context · decisions · outcomes</span>
</div>

<p class="section-intro">Longer-form notes on turning ambiguous, high-stakes platform problems into systems that teams can operate and evolve. Each story follows the same staff-level structure: context, stakes, judgment, alignment, result, and learning.</p>

<nav class="story-toc" aria-label="Story sections">
  <a href="#qualys">Qualys — Multi-cloud workload protection</a>
  <a href="#globant">Globant — Billing platform modernization</a>
  <a href="#casaone">CasaOne — Operations and logistics</a>
  <a href="#truesparrow">TrueSparrow — Token economy infrastructure</a>
</nav>

<div class="story-list story-page animate-in">

  <article class="story-item" id="qualys">
    <div class="story-rail"><span>01</span></div>
    <div class="story-main">
      <div class="story-header">
        <div><span class="story-company">Qualys</span><h3>Multi-cloud agentless workload protection</h3></div>
        <span class="story-period">2025 — Present</span>
      </div>

      <p class="story-lead">I architect the distributed engine behind Qualys FlexScan, which checks companies' cloud servers for security problems without installing anything on those servers. A scan starts in one place, then fans out into thousands of snapshot, discovery, and scan tasks across AWS, Azure, GCP, and OCI.</p>

      <div class="story-detail-grid">
        <div><strong>Context</strong><p>Agentless is a hard requirement: enterprise and government customers will not let a third-party tool run inside their production systems. We take a temporary, read-only copy of a server's disk, inspect it on a short-lived scanner we control, and then destroy everything. The real server is never touched, but the orchestration has to stay reliable while one customer's broad fleet scan produces a burst of work that could starve another customer's smaller scan.</p></div>
        <div><strong>Architecture</strong><p>Durable workflow state lives in Oracle. Kafka carries lifecycle events between services. Redis owns transient scheduling, per-tenant queues, delayed polling, and fairness budgets. Provider-specific workers translate the same lifecycle into AWS, Azure, GCP, and OCI primitives. The whole flow touches roughly 15–16 downstream services, so interfaces and contracts matter more than any single service's code.</p></div>
      </div>

      <div class="story-technical-note"><strong>Azure snapshot optimization</strong><span>AWS required copying a shared snapshot into our account before creating scanner storage. Azure lets a managed identity in our subscription create a snapshot that references the customer's managed disk ARM ID across subscriptions. We still create an attachable managed disk from that snapshot, but removing the separate cross-subscription copy step cut provisioning time by about 60% while preserving managed-identity RBAC, CMK-aware encryption, and deterministic cleanup.</span></div>

      <div class="story-technical-note"><strong>Resilient scanner provisioning</strong><span>When one Azure region suddenly could not allocate our configured scanner SKU, retries were amplifying the backlog. I separated containment (stop admitting work and suppress retries for non-transient SKU errors), recovery (validate a compatible alternate size against CPU, memory, disk count, architecture, image, and policy), and prevention (a regional capability catalog with ordered candidates and launch-time preflight checks). Self-healing without an alert creates hidden debt, so every fallback emits an operational event.</span></div>

      <div class="story-technical-note"><strong>Account-scoped AWS discovery</strong><span>Our orchestration looped through enabled regions and invoked every discovery function from inside that loop. Some AWS operations, such as listing S3 buckets, are account-scoped, so a 20-region customer repeated the same inventory traversal 20 times. I added operation-scope metadata (account, region, or resource) so account-scoped work runs once, resolves each resource's region, and fans results into the regional pipeline. The request saving is proportional to pagination; the real win is making external-call scope explicit.</span></div>

      <div class="story-technical-note"><strong>Kafka direct-memory incident</strong><span>A newly onboarded enterprise customer launched a broad scan across about 20 regions and the broker threw <code>OutOfMemoryError: Direct buffer memory</code>. Heap looked healthy, but direct-buffer pool usage, request bytes, and connection churn rose together. Containment throttled tenant and regional fan-out and stopped aggressive retries. Durable fixes combined claim-check references in Kafka, LZ4 compression, long-lived producer connections, and an explicit JVM/container memory envelope. More memory would have only moved the failure threshold; the real fix was workload shaping and admission control.</span></div>

      <div class="story-impact"><span><strong>100K+</strong> events/day</span><span><strong>100+</strong> environments</span><span><strong>60%</strong> faster provisioning</span><span><strong>15–16</strong> integrations</span></div>
      <div class="story-tech">Kafka · Redis · Oracle · Azure · AWS · GCP · OCI · Java · Node.js · Terraform</div>
    </div>
  </article>

  <article class="story-item" id="globant">
    <div class="story-rail"><span>02</span></div>
    <div class="story-main">
      <div class="story-header">
        <div><span class="story-company">Globant</span><h3>Billing platform modernization</h3></div>
        <span class="story-period">2021 — 2025</span>
      </div>

      <p class="story-lead">I led the incremental decomposition of a monolithic billing platform while preserving payment correctness, PCI boundaries, and delivery continuity across three international markets.</p>

      <div class="story-detail-grid">
        <div><strong>Context</strong><p>The platform supported Stripe and PayPal checkout, settlement reconciliation, and billing authorization. Tightly coupled workflows made a risky rewrite impossible, but continuing as-is meant every market expansion duplicated PCI-sensitive code and reconciliation work.</p></div>
        <div><strong>Approach</strong><p>I split the work by capability rather than frontend/backend silo: one owner for payment state and processor adapters, one for webhook/event handling and settlement, one for authorization and feature gating, and one for operational views. Each capability had a primary owner and a secondary reviewer, and we held failure-scenario reviews before code completion because payment bugs cluster at timeouts, retries, and duplicate webhooks.</p></div>
      </div>

      <div class="story-technical-note"><strong>Hosted tokenization and PCI scope</strong><span>Raw card data went directly from browser-hosted processor components to Stripe or PayPal. Our services stored only processor references and safe display metadata, backed by idempotency keys and a provider-neutral payment state machine. This materially reduced the cardholder-data environment, while keeping webhook signatures, TLS, CSP, and access control strict. Browser redirect is a UX signal; the webhook or server-side status is the source of truth.</span></div>

      <div class="story-technical-note"><strong>Settlement ledger</strong><span>Processor settlement files and webhooks can duplicate or arrive out of order, but finance needs an auditable answer for every difference. I separated Kafka's decoupling/replay role from the database's financial authority: a PostgreSQL transaction commits the inbox record, immutable balanced ledger entries, matching state, and outbox event together, then advances the Kafka offset. Exactly-once delivery is impossible; exactly-once effect is the goal.</span></div>

      <div class="story-technical-note"><strong>Policy-based authorization</strong><span>Billing authorization outgrew admin-versus-user roles. I built a deny-by-default layer with policy retrieval, information, and decision services. Feature gating became a first-class action in the same engine instead of a separate flag product, so enabling a feature for an account is an ordinary policy attachment with the same audit trail as any permission decision.</span></div>

      <div class="story-impact"><span><strong>$20M+</strong> annual volume</span><span><strong>15%</strong> faster checkout</span><span><strong>50%</strong> less manual ops</span><span><strong>40%</strong> less reconciliation</span></div>
      <div class="story-tech">Node.js · TypeScript · PostgreSQL · Kafka · Redis · Stripe · PayPal · NestJS</div>
    </div>
  </article>

  <article class="story-item" id="casaone">
    <div class="story-rail"><span>03</span></div>
    <div class="story-main">
      <div class="story-header">
        <div><span class="story-company">CasaOne</span><h3>Operations and logistics platform</h3></div>
        <span class="story-period">2020 — 2021</span>
      </div>

      <p class="story-lead">I reworked critical warehouse and inventory paths so operational systems could stay fast, event-driven, and resilient to unreliable third-party logistics partners.</p>

      <div class="story-detail-grid">
        <div><strong>Context</strong><p>Slow APIs, N+1 access patterns, and synchronous partner dependencies were creating warehouse backlogs and delaying inventory visibility. Core inventory state transitions were blocking on 3PL calls that had no SLA guarantee.</p></div>
        <div><strong>Architecture</strong><p>I combined query-plan and index analysis with GCP Pub/Sub state propagation. Partner adapters became idempotent and ran behind bounded retries with SLA-aware escalation. The core inventory write path no longer waited for a partner response; instead, the system accepted a state transition, published it, and reconciled asynchronously when the partner eventually responded.</p></div>
      </div>

      <div class="story-technical-note"><strong>Operational resilience</strong><span>Separating core state from partner latency meant a slow 3PL no longer blocked customer and warehouse workflows. We used query-plan analysis to replace sequential scans, batched N+1 lookups, and cached stable reference data without polluting write-heavy paths.</span></div>

      <div class="story-impact"><span><strong>9–13s → &lt;2s</strong> API latency</span><span><strong>30%</strong> less manual effort</span><span><strong>Real-time</strong> inventory sync</span></div>
      <div class="story-tech">GCP Pub/Sub · Node.js · MongoDB · Redis · Mocha</div>
    </div>
  </article>

  <article class="story-item" id="truesparrow">
    <div class="story-rail"><span>04</span></div>
    <div class="story-main">
      <div class="story-header">
        <div><span class="story-company">TrueSparrow</span><h3>Token economy infrastructure</h3></div>
        <span class="story-period">2018 — 2020</span>
      </div>

      <p class="story-lead">I built the backend for a platform that let companies launch branded token economies on Ethereum, plus the indexing and real-time systems that made blockchain data usable in real apps.</p>

      <div class="story-detail-grid">
        <div><strong>Context</strong><p>A blockchain is a secure, tamper-proof ledger, but it is a poor fit for fast questions like "what is this address's balance now?" Answering directly means scanning enormous history every time, which is far too slow for a product serving users.</p></div>
        <div><strong>Architecture</strong><p>I built REST APIs that hid blockchain complexity from client applications. A block scanner continuously read new Ethereum blocks, processed every transaction and token transfer, and wrote normalized data into a fast, query-oriented store. RabbitMQ worker pipelines handled retries and dead-letter cases, while Redis-backed real-time channels pushed state changes to clients.</p></div>
      </div>

      <div class="story-technical-note"><strong>Indexing and consistency</strong><span>The scanner had to survive crashes, network hiccups, and chain reorganizations without double-counting or losing transactions. I modeled progress explicitly and kept request acceptance separate from chain confirmation, so workers could retry safely while clients saw real-time state changes.</span></div>

      <div class="story-technical-note"><strong>Reusable cache library</strong><span>Across OST products, teams needed the same cache API with Redis in some environments, Memcached in others, and in-process storage for local development. I helped build a factory/strategy layer with shared validation, serialization, TTL, multi-get, and counters while preserving backend-specific semantics rather than pretending every store behaves identically.</span></div>

      <div class="story-impact"><span><strong>10K+</strong> monthly active users</span><span><strong>25%</strong> more blockchain throughput</span><span><strong>3</strong> open-source systems</span></div>
      <div class="story-tech">Web3.js · RabbitMQ · Node.js · MySQL · DynamoDB · Cassandra · Redis</div>
    </div>
  </article>

</div>

<p class="section-cta animate-in"><a class="button" href="/projects/">See the public projects and research</a></p>
