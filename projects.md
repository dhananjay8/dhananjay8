---
layout: default
title: Projects
description: Open source projects and public engineering work by Dhananjay Patil.
permalink: /projects/
---

<div class="section-header">
  <h2>Selected engineering work</h2>
  <span class="section-tag">architecture · systems · AI</span>
</div>

<p style="color: var(--text-sub); margin-bottom: 2rem;">A focused portfolio of systems spanning multi-tenant SaaS, constrained AI evaluation, conversational retrieval, and real-time streaming security.</p>

<div class="project-spectrum animate-in" aria-label="System architecture spectrum">
  <div><span>Platform</span><strong>Operate compliance</strong><small>Continuous lifecycle</small></div>
  <div><span>Engine</span><strong>Audit policies</strong><small>Rule-by-rule evaluation</small></div>
  <div><span>Interface</span><strong>Answer questions</strong><small>Conversational access</small></div>
  <div><span>Sentinel</span><strong>Detect anomalies</strong><small>Always-on runtime defense</small></div>
</div>

## Flagship systems

<div class="oss-grid flagship-grid animate-in">
  <article class="oss-card featured system-card">
    <div class="system-card-top"><span class="system-type">The platform</span><span>Multi-tenant SaaS</span></div>
    <div class="oss-card-header">
      <a href="https://github.com/dhananjay8/compliance-automation-prototype" target="_blank" rel="noopener">Continuous Compliance Automation</a>
    </div>
    <p>A Vanta-like operating system for compliance teams: integrations continuously sync cloud resources, deterministic rules test controls, evidence is collected and expires, drift is detected, and framework readiness rolls up for audits.</p>
    <dl class="system-facts">
      <div><dt>Persona</dt><dd>Compliance managers</dd></div><div><dt>Output</dt><dd>Posture, evidence, audit trails</dd></div><div><dt>Intelligence</dt><dd>Rules first; optional RAG</dd></div>
    </dl>
    <div class="tech-tags"><span class="tech-tag purple">FastAPI</span><span class="tech-tag blue">PostgreSQL</span><span class="tech-tag">Redis/RQ</span><span class="tech-tag">APScheduler</span><span class="tech-tag">OIDC/SCIM</span></div>
  </article>

  <article class="oss-card featured system-card">
    <div class="system-card-top"><span class="system-type">The auditor</span><span>Batch evaluation</span></div>
    <div class="oss-card-header">
      <a href="https://github.com/dhananjay8/compliance-evaluator" target="_blank" rel="noopener">Compliance Evaluator</a>
    </div>
    <p>Deep policy-document audit engine that evaluates PDFs rule by rule with hybrid retrieval and constrained LLM judgments. A verdict is compliant only when explicit evidence survives deterministic, verbatim citation validation.</p>
    <dl class="system-facts">
      <div><dt>Persona</dt><dd>Auditors</dd></div><div><dt>Output</dt><dd>Binary verdicts and gaps</dd></div><div><dt>Guarantee</dt><dd>LLM proposes; code disposes</dd></div>
    </dl>
    <div class="tech-tags"><span class="tech-tag accent">LangGraph</span><span class="tech-tag blue">Elasticsearch</span><span class="tech-tag">kNN + BM25</span><span class="tech-tag">Ollama</span><span class="tech-tag">PyMuPDF</span></div>
  </article>

  <article class="oss-card featured system-card">
    <div class="system-card-top"><span class="system-type">The interface</span><span>Conversational RAG</span></div>
    <div class="oss-card-header">
      <a href="https://github.com/dhananjay8/langgraph-policy-qa-poc" target="_blank" rel="noopener">Grounded Policy Q&amp;A on Azure</a>
    </div>
    <p>Azure-native policy assistant with thread memory, hybrid retrieval, reranking, self-correction, SSE progress, and citation grounding. Deterministic contracts and DeepEval metrics make answer quality observable rather than anecdotal.</p>
    <dl class="system-facts">
      <div><dt>Persona</dt><dd>Employees</dd></div><div><dt>Output</dt><dd>Cited answers</dd></div><div><dt>Runtime</dt><dd>Interactive, multi-turn</dd></div>
    </dl>
    <div class="tech-tags"><span class="tech-tag accent">LangGraph</span><span class="tech-tag blue">Azure OpenAI</span><span class="tech-tag">FAISS</span><span class="tech-tag">SSE</span><span class="tech-tag">OpenTelemetry</span></div>
  </article>

  <article class="oss-card featured system-card">
    <div class="system-card-top"><span class="system-type">The sentinel</span><span>Streaming security</span></div>
    <div class="oss-card-header">
      <a href="https://github.com/dhananjay8/runtime-anomaly-platform" target="_blank" rel="noopener">eBPF Runtime Anomaly Platform</a>
    </div>
    <p>Five-service, streaming-first container security system: eBPF probes capture syscalls, process execution, and network activity; Kafka carries events through ingestion and 30-second feature windows; Isolation Forest produces explainable alerts with sub-second kernel-to-detection latency.</p>
    <dl class="system-facts">
      <div><dt>Telemetry</dt><dd>Zero-instrumentation eBPF</dd></div><div><dt>Detection</dt><dd>18 behavioral features</dd></div><div><dt>Reliability</dt><dd>DLTs, idempotency, circuit breakers</dd></div>
    </dl>
    <div class="tech-tags"><span class="tech-tag accent">Kafka</span><span class="tech-tag">eBPF/BCC</span><span class="tech-tag purple">Spring Boot</span><span class="tech-tag">Isolation Forest</span><span class="tech-tag">Oracle</span></div>
  </article>
</div>

## Selected systems

<div class="oss-grid animate-in">
  <div class="oss-card">
    <div class="oss-card-header">
      <a href="https://github.com/dhananjay8/custom-rate-limiter" target="_blank" rel="noopener">Custom Rate Limiter</a>
    </div>
    <p>Six interchangeable algorithms, distributed storage, adaptive limits, weighted quotas, circuit-breaker resilience, Prometheus metrics, runtime configuration, and Azure infrastructure—backed by 202 tests.</p>
    <div class="tech-tags"><span class="tech-tag purple">Python</span><span class="tech-tag">Redis</span><span class="tech-tag">Flask</span><span class="tech-tag blue">Azure Bicep</span></div>
  </div>
  <div class="oss-card">
    <div class="oss-card-header">
      <a href="/papers/aws-lambda-concurrency/">Comparative research of various Concurrency Techniques for Serverless Cloud Services</a>
    </div>
    <p>Reproducible study comparing reserved concurrency, provisioned concurrency, burst limiting, and queue-based load leveling through calibrated simulation and a runnable CloudWatch measurement harness.</p>
    <div class="tech-tags"><span class="tech-tag accent">AWS Lambda</span><span class="tech-tag purple">Python</span><span class="tech-tag">Simulation</span><span class="tech-tag">CloudWatch</span></div>
  </div>
</div>

<p class="section-cta animate-in"><a class="button" href="https://github.com/dhananjay8?tab=repositories" target="_blank" rel="noopener">View all repositories on GitHub</a></p>
