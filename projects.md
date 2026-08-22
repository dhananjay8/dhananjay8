---
layout: default
title: Projects
description: Open source projects and public engineering work by Dhananjay Patil.
permalink: /projects/
---

<div class="section-header">
  <h2>Projects &amp; Open Source</h2>
  <span class="section-tag">public work</span>
</div>

<p style="color: var(--text-sub); margin-bottom: 2rem;">Open source contributions and personal engineering projects.</p>

<div class="oss-grid animate-in">
  <div class="oss-card featured">
    <div class="oss-card-header">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0 1 12 6.844a9.59 9.59 0 0 1 2.504.337c1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.02 10.02 0 0 0 22 12.017C22 6.484 17.522 2 12 2z"/></svg>
      <a href="https://github.com/dhananjay8/compliance-automation-prototype" target="_blank" rel="noopener">dhananjay8 / compliance-automation-prototype</a>
    </div>
    <p>Vanta-like continuous compliance automation prototype. FastAPI backend with Pydantic v2, PostgreSQL schema, rule engine, worker, evidence store, RAG pipeline for compliance Q&A, and seed data for SOC 2, ISO 27001, GDPR, HIPAA, PCI DSS, CIS, and NIST. Includes Podman-based local tests and seed-data validation.</p>
    <div class="tech-tags"><span class="tech-tag purple">Python</span><span class="tech-tag accent">FastAPI</span><span class="tech-tag blue">PostgreSQL</span><span class="tech-tag">Pydantic</span><span class="tech-tag">RAG</span><span class="tech-tag">Docker</span></div>
  </div>
  <div class="oss-card featured">
    <div class="oss-card-header">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0 1 12 6.844a9.59 9.59 0 0 1 2.504.337c1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.02 10.02 0 0 0 22 12.017C22 6.484 17.522 2 12 2z"/></svg>
      <a href="https://github.com/dhananjay8/custom-rate-limiter" target="_blank" rel="noopener">dhananjay8 / custom-rate-limiter</a>
    </div>
    <p>Production-grade Python rate limiting framework with 6 algorithms (Fixed Window, Sliding Log, Sliding Window Counter, Token Bucket, Leaky Bucket, GCRA), 3 storage backends, adaptive limiting, weighted/coalesced requests, quota sharing, circuit breaker resilience, dry-run diagnostics, Azure Bicep infra, CI/CD, and OpenAPI/Swagger docs. 202 tests, 87% coverage.</p>
    <div class="tech-tags"><span class="tech-tag purple">Python</span><span class="tech-tag">Flask</span><span class="tech-tag">Redis</span><span class="tech-tag">SQLite</span><span class="tech-tag">Azure Bicep</span><span class="tech-tag orange">pytest</span></div>
  </div>
  <div class="oss-card featured">
    <div class="oss-card-header">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><path d="M12 18v-6"/><path d="M8 15l4-3 4 3"/></svg>
      <a href="/papers/aws-lambda-concurrency/">dhananjay8 / aws-lambda-concurrency-research</a>
    </div>
    <p>Research paper and reproducible artifact on AWS Lambda concurrency challenges. Survey, challenge taxonomy, four mitigation patterns, calibrated discrete-time simulation, and a runnable E2E AWS measurement harness.</p>
    <div class="tech-tags"><span class="tech-tag purple">Python</span><span class="tech-tag accent">AWS Lambda</span><span class="tech-tag">Simulation</span><span class="tech-tag">CloudWatch</span><span class="tech-tag">Research</span></div>
  </div>
  <div class="oss-card">
    <div class="oss-card-header">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0 1 12 6.844a9.59 9.59 0 0 1 2.504.337c1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.02 10.02 0 0 0 22 12.017C22 6.484 17.522 2 12 2z"/></svg>
      <a href="https://github.com/TrueSparrowSystems/UniCache" target="_blank" rel="noopener">TrueSparrowSystems / UniCache</a>
    </div>
    <p>Universal caching library with adapters for Memcached, Redis, and in-memory storage through a unified interface. Core contributor.</p>
    <div class="tech-tags"><span class="tech-tag accent">Node.js</span><span class="tech-tag">Redis</span><span class="tech-tag">Memcached</span></div>
  </div>
  <div class="oss-card">
    <div class="oss-card-header">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0 1 12 6.844a9.59 9.59 0 0 1 2.504.337c1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.02 10.02 0 0 0 22 12.017C22 6.484 17.522 2 12 2z"/></svg>
      <a href="https://github.com/dhananjay8/runtime-anomaly-platform" target="_blank" rel="noopener">dhananjay8 / runtime-anomaly-platform</a>
    </div>
    <p>Distributed eBPF runtime fingerprinting and anomaly detection for containerized workloads. Isolation Forest ML model, Kafka ingestion pipeline, Spring Boot REST APIs.</p>
    <div class="tech-tags"><span class="tech-tag accent">Kafka</span><span class="tech-tag">eBPF</span><span class="tech-tag purple">Spring Boot</span><span class="tech-tag">scikit-learn</span></div>
  </div>
  <div class="oss-card">
    <div class="oss-card-header">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0 1 12 6.844a9.59 9.59 0 0 1 2.504.337c1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.02 10.02 0 0 0 22 12.017C22 6.484 17.522 2 12 2z"/></svg>
      <a href="https://github.com/dhananjay8/mark-and-sweep-algorithm" target="_blank" rel="noopener">dhananjay8 / mark-and-sweep-algorithm</a>
    </div>
    <p>Educational garbage collector with object graph traversal, memory state visualization, interactive demos, and pytest coverage.</p>
    <div class="tech-tags"><span class="tech-tag purple">Python</span><span class="tech-tag">pytest</span></div>
  </div>
  <div class="oss-card featured">
    <div class="oss-card-header">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0 1 12 6.844a9.59 9.59 0 0 1 2.504.337c1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.02 10.02 0 0 0 22 12.017C22 6.484 17.522 2 12 2z"/></svg>
      <span>dhananjay8 / green-cloud-metrics</span>
    </div>
    <p>Azure cloud sustainability analytics and carbon footprint measurement tooling. Energy tracking, resource tagging, and cost-aware environmental reports. <em style="color: var(--text-muted);">Repository coming soon.</em></p>
    <div class="tech-tags"><span class="tech-tag blue">Azure</span><span class="tech-tag purple">Python</span><span class="tech-tag">Sustainability</span></div>
  </div>
  <div class="oss-card">
    <div class="oss-card-header">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0 1 12 6.844a9.59 9.59 0 0 1 2.504.337c1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.02 10.02 0 0 0 22 12.017C22 6.484 17.522 2 12 2z"/></svg>
      <a href="https://github.com/ostdotcom" target="_blank" rel="noopener">ostdotcom / OST ecosystem</a>
    </div>
    <p>Contributed to OST Cache, OST Block Scanner, and OST View — backend infrastructure and tooling for a blockchain token economy platform.</p>
    <div class="tech-tags"><span class="tech-tag orange">Web3</span><span class="tech-tag purple">Node.js</span><span class="tech-tag">Blockchain</span></div>
  </div>
</div>
