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

<p style="color: var(--text-sub); margin-bottom: 2rem;">A focused selection of systems that demonstrate architecture leadership, reliability engineering, cloud security, and production-minded AI.</p>

## Flagship systems

<div class="oss-grid animate-in">
  <div class="oss-card featured">
    <div class="oss-card-header">
      <a href="https://github.com/dhananjay8/compliance-evaluator" target="_blank" rel="noopener">Compliance Evaluator</a>
    </div>
    <p>Local-first policy evaluation platform with hybrid kNN/BM25 retrieval, LangGraph orchestration, deterministic citation enforcement, prompt-injection defenses, and traceable compliance verdicts. Designed so model output never overrides system guarantees.</p>
    <div class="tech-tags"><span class="tech-tag purple">Python</span><span class="tech-tag accent">LangGraph</span><span class="tech-tag blue">Elasticsearch</span><span class="tech-tag">Ollama</span><span class="tech-tag">FastAPI</span></div>
  </div>
  <div class="oss-card featured">
    <div class="oss-card-header">
      <a href="https://github.com/dhananjay8/langgraph-policy-qa-poc" target="_blank" rel="noopener">Grounded Policy Q&amp;A on LangGraph &amp; Azure</a>
    </div>
    <p>Production-deployed RAG service with deterministic verbatim-citation validation, managed identity, distributed traces, and live DeepEval quality gates. Separates probabilistic generation from deterministic correctness checks.</p>
    <div class="tech-tags"><span class="tech-tag purple">Python</span><span class="tech-tag accent">LangGraph</span><span class="tech-tag blue">Azure</span><span class="tech-tag">OpenTelemetry</span><span class="tech-tag">DeepEval</span></div>
  </div>
  <div class="oss-card featured">
    <div class="oss-card-header">
      <a href="https://github.com/dhananjay8/compliance-automation-prototype" target="_blank" rel="noopener">Continuous Compliance Automation</a>
    </div>
    <p>Multi-tenant compliance platform spanning framework normalization, resource ingestion, rule evaluation, evidence, audit workflows, and grounded compliance Q&amp;A. Includes validated seed data and containerized integration flows.</p>
    <div class="tech-tags"><span class="tech-tag purple">Python</span><span class="tech-tag accent">FastAPI</span><span class="tech-tag blue">PostgreSQL</span><span class="tech-tag">RAG</span><span class="tech-tag">Podman</span></div>
  </div>
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
      <a href="https://github.com/dhananjay8/runtime-anomaly-platform" target="_blank" rel="noopener">Runtime Anomaly Platform</a>
    </div>
    <p>Distributed runtime-security pipeline combining eBPF fingerprints, Kafka ingestion, Isolation Forest scoring, persistence, and Spring Boot APIs for container workload anomaly detection.</p>
    <div class="tech-tags"><span class="tech-tag accent">Kafka</span><span class="tech-tag">eBPF</span><span class="tech-tag purple">Spring Boot</span><span class="tech-tag">scikit-learn</span></div>
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
