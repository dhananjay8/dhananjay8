---
layout: default
title: AWS Lambda Concurrency Research
description: Survey and simulation-based evaluation of concurrency challenges in AWS Lambda — reserved/provisioned concurrency, burst limiter, and queue-based load leveling.
permalink: /papers/aws-lambda-concurrency/
---

<div class="section-header">
  <h2>Concurrency Challenges in AWS Lambda</h2>
  <span class="section-tag">research paper</span>
</div>

<p style="color: var(--text-sub); margin-bottom: 2rem;">A survey and simulation-based evaluation of AWS Lambda concurrency controls: reserved concurrency, provisioned concurrency, the token-bucket burst limiter, and queue-based load leveling.</p>

## Abstract

AWS Lambda abstracts server management but exposes a non-trivial concurrency model. Under bursty or multi-tenant workloads the interaction of reserved concurrency, provisioned concurrency, and the token-bucket burst limiter determines whether a system degrades gracefully or fails hard with throttling.

This study surveys the concurrency model and documented failure modes, proposes a five-class challenge taxonomy (C1–C5), synthesizes four dominant mitigation patterns, and evaluates their trade-offs with a calibrated, deterministic discrete-time simulation. Results are paired with a runnable end-to-end AWS measurement harness so the simulated conclusions can be reproduced or superseded with live CloudWatch data.

## Key contributions

1. A **concurrency-challenge taxonomy** (C1–C5) grounded in AWS operator documentation and independent academic measurements.
2. A **synthesis of mitigation patterns**: on-demand baseline, reserved-concurrency isolation, provisioned concurrency, and queue-based load leveling.
3. A **calibrated discrete-time simulation** whose cold-start, burst-limit, and pricing parameters are drawn from published AWS documentation and peer-reviewed measurement studies.
4. A **runnable E2E measurement harness** that deploys a real Lambda function and pulls CloudWatch metrics.
5. **Cross-validation** of simulation outputs against independent public benchmarks, with an explicit threats-to-validity discussion.

## Methodology

The evaluation uses two complementary paths:

- **Path A — real E2E harness**: packages and deploys a Lambda function, applies reserved/provisioned concurrency, drives concurrent load, and pulls `ConcurrentExecutions`, `Throttles`, `Errors`, and `Duration` metrics from CloudWatch.
- **Path B — calibrated simulation**: a discrete-time model at 50 ms resolution that simulates Poisson arrivals, warm-environment reuse, a hard concurrency ceiling, a token-bucket burst limiter, optional provisioned concurrency, and optional bounded queueing.

All scenarios share the same step-burst arrival process so only the concurrency-control configuration differs.

## Results at a glance

### Outcome rates

| Scenario | Success rate | Throttle rate |
|---|---|---|
| Baseline on-demand | 76.5% | 23.5% |
| Reserved isolated | 69.7% | 30.3% |
| Provisioned | 97.2% | 2.8% |
| Queue buffered | 100.0% | 0.0% |

### End-to-end latency (ms)

| Scenario | p50 | p95 | p99 |
|---|---|---|---|
| Baseline on-demand | 276 | 441 | 541 |
| Reserved isolated | 276 | 441 | 546 |
| Provisioned | 275 | 440 | 537 |
| Queue buffered | 16,180 | 23,024 | 23,700 |

`queue_buffered` achieves perfect success rate because buffering redistributes overload in time; the multi-second latency is queue wait, not processing time. `provisioned` gives the best synchronous-API combination of high success and low tail latency.

## Practical guidance

- **Bursty, latency-tolerant async workloads** → queue-based load leveling is the highest-reliability, lowest-effort mitigation, but size the queue so it drains within the acceptable wait bound.
- **Bursty synchronous APIs** → provisioned concurrency removes most cold starts and delivers stable p95 latency; cost scales with pre-warmed capacity.
- **Multi-tenant accounts** → reserved concurrency isolates functions from noisy neighbors, but undersizing it adds a local throttling ceiling on top of the burst limiter.

## Links

- <a href="https://github.com/dhananjay8/aws-lambda-concurrency-research" target="_blank" rel="noopener">GitHub repository</a> — public release coming soon
- <a href="https://medium.com/globant/introduction-to-rabbitmq-5af1a58b942e" target="_blank" rel="noopener">Related writing: Introduction to RabbitMQ</a>

<p style="margin-top: 2rem; color: var(--text-muted); font-size: 0.875rem; font-style: italic;">All simulated results use a fixed random seed (42) and are fully reproducible via <code>python -m sim.run_all</code>.</p>
