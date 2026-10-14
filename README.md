# Ernesto Villarreal Ibarra

**Full Stack Developer · DevOps** — Ciudad Juárez, México

I build platforms that go into production, and then I make them observable. Right now I'm the
only developer behind an institutional platform that has grown to seven applications on a single
FastAPI monolith, plus the graduate-studies platform next to it — and I run the Prometheus /
Loki / Tempo / Grafana stack that watches both. Competitive programmer: 2× ICPC Mexico Finals,
2× state champion.

[![Portfolio](https://img.shields.io/badge/Portfolio-erne1357.me-00f5d4?style=flat-square&logo=firefox-browser&logoColor=white)](https://erne1357.me)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ernesto-villarreal-ibarra-49a443337/)
[![Email](https://img.shields.io/badge/Email-villarreal.i.ernesto%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:villarreal.i.ernesto@gmail.com)

---

## What I'm working on

**Developer (Honorarios) · ITCJ — Instituto Tecnológico de Ciudad Juárez** · Aug 2025 – Present

Sole developer of the institute's digital platform: a modular FastAPI monolith where seven
applications — help desk, course add/drop scheduling, maintenance, graduation, directory,
donations and a shared inventory core — live behind one JWT auth core and a role-centric
authorization backbone. Zero-downtime blue-green deploys, PgBouncer pooling, multi-worker
Socket.IO over Redis, 96 Alembic revisions and a CI gate over a 455-file pytest suite.

I also own the observability side: the application exports its own RED metrics, saturation
signals and presence data, emits OpenTelemetry traces, and writes JSON logs carrying `trace_id`
so a slow request can be followed from a log line straight into its span.

**Full Stack Developer · DevOps · Terabytio** · Apr 2026 – Aug 2026

Joined a startup team as a full stack developer and took over the infrastructure and
observability side of the business; in the final stretch the team recognized me as its DevOps.
Built the internal operations panel (Laravel 13 · Filament 5 · Livewire 4) that became the
source of truth for infrastructure, recurring cost and product attribution, and designed
fleet-wide observability where every host pushes metrics and logs over a private tailnet — no
host exposing a new port to the internet.

---

## Selected work

| Project | What it is | Stack |
|---|---|---|
| **[ITCJ Platform](https://github.com/Erne1357/itcj)** | Institutional platform: 7 apps in one modular monolith behind a shared auth core. 838 routes, 127 tables, 455 test files. | FastAPI · SQLAlchemy 2.0 · PostgreSQL · PgBouncer · Redis · Socket.IO · Celery · Docker |
| **[SIIAP](https://github.com/Erne1357/SIIAP)** | Full graduate student lifecycle — admission → permanence → graduation — with committee deliberation, document review workflows and granular delegable permissions. | Flask · PostgreSQL · Celery · Redis · Socket.IO · Docker · GitHub Actions |
| **Observability Stack** *(private)* | Metrics, logs and traces for the server shared by both platforms: 12 services, 37 alert rules, 3 dashboards, tail sampling, log↔trace correlation. | Prometheus · Loki · Tempo · Grafana · Alloy · OpenTelemetry |
| **Ops Panel** *(private, internal)* | Infrastructure inventory, multi-currency recurring cost, a credential vault that stores references instead of secrets, and live fleet observability inside the app. | Laravel 13 · Filament 5 · Livewire 4 · PostgreSQL 17 · Redis 7 · Tailscale |
| **[DeferAplication](https://github.com/Erne1357/deferAplication)** | Desktop business management system for a private client: multi-variant inventory, production recipes, credit sales, PDF reports. | C# · .NET 6 · WinForms · PostgreSQL |
| **[Portfolio](https://github.com/Erne1357/portfolio)** | This profile's companion site — bilingual, API-driven, deployed behind Nginx with Let's Encrypt. | React · TypeScript · Vite · FastAPI · Docker |

---

## Observability, specifically

The part of my work that is hardest to see from a repo list, so here it is:

- **Instrumenting applications, not just hosts.** RED metrics per app, top routes by p95 and by
  volume, and saturation signals that name the culprit — anyio and asyncio threadpools, DB pool,
  event-loop lag — instead of a CPU graph that only says "something is slow".
- **Distributed tracing with honest sampling.** Tail sampling keeps the slow and the failed
  traces plus a probabilistic baseline, and the decision windows are documented so a
  *trace not found* reads as expected behaviour rather than an outage.
- **Correlation that actually works.** `trace_id` travels in the JSON logs, so Loki jumps to
  Tempo and back; async tasks are traced as their own traces with span links to the request
  that enqueued them.
- **Alerts you can trust.** Prometheus rules covered by `promtool` unit tests, dashboards linted
  in CI, and deploys that run preflight → apply → smoke with automatic rollback.
- **Private by default.** Fleet agents push over a private tailnet; the stack binds to localhost
  and is reached over an SSH tunnel instead of putting one more Grafana on the internet.

---

## Stack

**Backend**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![PHP](https://img.shields.io/badge/PHP_8.4-777BB4?style=flat-square&logo=php&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel_13-FF2D20?style=flat-square&logo=laravel&logoColor=white)
![C#](https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=dotnet&logoColor=white)

**Data**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy_2.0-D71F00?style=flat-square&logo=sqlalchemy&logoColor=white)
![PgBouncer](https://img.shields.io/badge/PgBouncer-2D3A4A?style=flat-square)

**Observability & DevOps**
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![Loki](https://img.shields.io/badge/Loki-F5A800?style=flat-square&logo=grafana&logoColor=white)
![Tempo](https://img.shields.io/badge/Tempo-FF9900?style=flat-square&logo=grafana&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-425CC7?style=flat-square&logo=opentelemetry&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)

**Frontend**
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Livewire](https://img.shields.io/badge/Livewire_4-FB70A9?style=flat-square&logo=livewire&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap_5-7952B3?style=flat-square&logo=bootstrap&logoColor=white)

---

## Competitive programming

| Result | Event | Year |
|---|---|---|
| 74 / 120 | ICPC Mexico Finals | 2024 |
| 44 / 60 | ICPC Mexico Finals | 2023 |
| 🥇 1st place | interTecNM Chihuahua State Programming Contest | 2024 |
| 🥇 1st place | interTecNM Chihuahua State Programming Contest | 2023 |

Two consecutive ICPC Mexico Finals and back-to-back state titles. C++ is where I compete;
Python is where I ship.

---

## Education & certifications

- **B.S. in Computer Systems Engineering** — ITCJ, 2021–2025 (graduated)
- **Technical Diploma in Programming** — CBTIS 114, 2018–2021
- **CCNAv7: Introduction to Networks** — Cisco Networking Academy, 2024

---

<sub>Coding since 2018 · Open to backend, platform and DevOps/SRE roles · Spanish (native) · English (professional)</sub>
