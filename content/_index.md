---
title: Resume
---

# Muhamad Enrinal Zulhimar

Senior Backend Engineer · Jakarta, Indonesia (open to remote / relocation)
<br>[enrinaal@gmail.com](mailto:enrinaal@gmail.com) · [linkedin.com/in/enrinal](https://www.linkedin.com/in/enrinal) · [github.com/enrinal](https://github.com/enrinal)

## Summary

Senior Backend Engineer with 8+ years building and operating high-traffic distributed systems in Go and Java (Project Reactor / reactive) across OTA, logistics, fintech, and edtech. Specialize in booking and transaction services where correctness, idempotency, and fault tolerance are non-negotiable. Currently own the architecture for several services in Tiket.com's flight booking domain (millions of users, 100k+ bookings/day) and serve as acting tech lead for a 5-engineer squad—driving design reviews, ADRs, and incident response. Comfortable operating async in distributed, multicultural teams.

## Experience

### Tiket.com

Senior Software Engineer, Backend → Acting Tech Lead (Flight) · Aug 2022 – Present · Jakarta

- Serve as acting tech lead for a 5-engineer squad and technical owner of the booking domain: governing design reviews, authoring ADRs, and acting as the primary POC for cross-team integrations while leading on-call operations, post-mortems, and backend interviews.
- Own and operate multiple high-scale Go and Reactive Java (Project Reactor) backend services—including the core flight service—serving millions of travelers and 100k+ daily bookings. Designed system architecture to fan out to 5 downstream domains and sustain 5x traffic surges during holiday peaks.
- Cut p99 latency 40% and infra cost ~30% by consolidating fragmented MongoDB databases into a single cluster, then eliminating the resulting cross-DB joins via denormalized embedded documents and application-side batching—maintaining optimal read performance despite the merge.
- Reduced Redis memory footprint ~75% via Brotli payload compression and introduced traffic-adaptive cache TTLs with randomized jitter to prevent cache stampede during peak load—lowering cache-tier cost and tail latency.
- Decoupled highly coupled legacy flight services into distinct, domain-bounded microservices and standardized shared internal libraries across squads—enabling parallel feature delivery and cutting new-engineer ramp-up ~35%.
- Designed a declarative add-on pricing engine evaluating JSON-defined rules via recursive boolean expression trees (AND/OR), enabling no-code logic deployment with deterministic auditing and safe fallback; lifted upsell conversion ~13% with zero SLA regression.
- Designed and shipped the Master Bundling Generator to capture unaddressed upsell revenue by creating proprietary, middle-tier fares not offered by airlines. Engineered a hybrid architecture driven by a weighted rule engine that synthesizes and scores custom bundles, running real-time gap testing against high-ceiling airline fares during checkout via live APIs to dynamically surface the optimal package.
- Led the Flight × Hotel cross-vertical bundling project, engineering a Go-based Saga orchestrator to execute atomic all-or-nothing transactions with automatic compensating cancellations, completely eliminating charged-but-unbooked orders.
- Partnered with SRE to drive an observability overhaul (structured logging, distributed tracing, RED/USE dashboards, and SLO burn-rate alerts), reducing incident root-cause analysis time from hours to minutes.

### Ruangguru

Backend Engineering Instructor (Part-time / Seasonal) · Feb 2022 – Jul 2024 · Jakarta

- Authored end-to-end curriculum on scalable backend architecture, Go idioms, and production engineering; mentored 5 cohorts (Kampus Merdeka Batch 2–6) through hands-on backend projects.

### SiCepat Express

Software Engineer, Backend · Jul 2021 – Jul 2022 · Jakarta

- Built distributed shipment-tracking services on Kafka and Redis with at-least-once delivery and idempotent consumers, reducing duplicate and lost tracking events and improving shipment-status accuracy ~25%.
- Delivered an OCR-based ID verification pipeline at 90% SLA, automating manual review and cutting merchant onboarding time ~50%.

### Warung Pintar

Software Engineer, Backend · Jan 2020 – Jul 2021 · Jakarta

- Engineered the event-driven backend for the merchant sales platform, scaling cleanly as GMV grew 60% within 6 months of launch.
- Launched Kafka-based async notification and wallet services handling 100k+ messages/day, supporting a 50% rise in transaction volume.

### Angsur

Software Engineer · Jan 2018 – Oct 2019 · Bandar Lampung

- Built RESTful services and admin dashboards for a Sharia fintech credit platform, streamlining underwriting to cut credit-validation cycle time ~30%.

## Skills

- **Languages:** Go, Java, Python, SQL
- **Distributed systems:** Microservices, Event-Driven Architecture, Sagas, CQRS, High Availability, Idempotency & Fault Tolerance, Caching Strategies, Observability (logs, traces, metrics), SLO/SLI design
- **Infrastructure:** Kafka, NATS, Redis, MongoDB, PostgreSQL, Elasticsearch, Docker, Kubernetes, gRPC, GraphQL
- **Practices:** System Design, Architecture Decision Records, Design & Code Review, Incident Management, On-call, Technical Hiring

## Education

### Institut Teknologi Sumatera

Bachelor of Informatics Engineering · Aug 2016 – Sep 2020 · Bandar Lampung

Cum Laude, GPA 3.66 / 4.00

## Awards & Leadership

- **ICPC Asia–Jakarta Regional Programming Contest** — Regional Finalist (21st)
- **President (Ketua)**, Electrical & Informatics Engineering Student Association (HMEI), ITERA · 2018–2019 — led the student association; ran the HMEI Mengabdi mentorship and community-outreach program.
