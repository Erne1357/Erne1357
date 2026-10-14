# Ernesto Villarreal Ibarra

**Full Stack Developer · DevOps** — Ciudad Juárez, México

I'm the only developer on the platform at ITCJ: seven apps on one FastAPI monolith, plus SIIAP,
the graduate-studies platform next to it. I also set up and run the monitoring for both —
Prometheus, Loki, Tempo and Grafana. Before that I did the same for a server fleet at Terabytio.
Two ICPC Mexico Finals with the institute's team.

[![Portfolio](https://img.shields.io/badge/Portfolio-erne1357.me-00f5d4?style=flat-square&logo=firefox-browser&logoColor=white)](https://erne1357.me)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ernesto-villarreal-ibarra-49a443337/)
[![Email](https://img.shields.io/badge/Email-villarreal.i.ernesto%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:villarreal.i.ernesto@gmail.com)

---

## What I'm working on

**Developer (Honorarios) · ITCJ — Instituto Tecnológico de Ciudad Juárez** · Aug 2025 – Present

Seven apps in one FastAPI monolith — help desk, course add/drop scheduling, maintenance,
graduation, directory, donations and a shared inventory — all behind the same login and the same
permission system, over ~127 tables. Deploys are blue-green with no downtime, PgBouncer sits in
front of Postgres, Socket.IO runs across workers over Redis, and CI runs a 455-file pytest suite.

I also wrote the instrumentation inside the app: requests and error rate per app, how full the
database pool and the threadpools are, event-loop lag, and OpenTelemetry traces whose `trace_id`
is printed in the logs, so from a log line you can jump to the trace of that exact request.

**Full Stack Developer · DevOps · Terabytio** · Apr 2026 – Aug 2026

I joined as a full stack developer and ended up taking the infrastructure and the monitoring; for
the last month and a half the team treated me as the DevOps. I built the internal ops panel
(Laravel 13, Filament 5, Livewire 4) that replaced the spreadsheets where servers, costs,
products and clients were tracked, and set up monitoring for the whole fleet: an agent on each
host pushing metrics and logs through a private network, so no host had to open a port to the
internet.

---

## Selected work

| Project | What it is | Stack |
|---|---|---|
| **[ITCJ Platform](https://github.com/Erne1357/itcj)** | Seven apps in one modular monolith behind a shared login. 838 routes, 127 tables, 455 test files. | FastAPI · SQLAlchemy 2.0 · PostgreSQL · PgBouncer · Redis · Socket.IO · Celery · Docker |
| **[SIIAP](https://github.com/Erne1357/SIIAP)** | Admission, permanence and graduation for the graduate programs: document review, committee voting, delegable permissions. | Flask · PostgreSQL · Celery · Redis · Socket.IO · Docker · GitHub Actions |
| **Monitoring stack** *(private)* | Metrics, logs and traces for the server ITCJ and SIIAP share: 12 services, 37 alert rules, 3 dashboards, tail sampling, log↔trace correlation. | Prometheus · Loki · Tempo · Grafana · Alloy · OpenTelemetry |
| **Ops panel** *(private, internal)* | Servers, domains, storage and what each one costs per month, an access vault that stores references instead of passwords, and live host metrics inside the app. | Laravel 13 · Filament 5 · Livewire 4 · PostgreSQL 17 · Redis 7 · Tailscale |
| **[DeferAplication](https://github.com/Erne1357/deferAplication)** | Desktop system for a private client: multi-variant inventory, production recipes, credit sales, PDF reports. | C# · .NET 6 · WinForms · PostgreSQL |
| **[Portfolio](https://github.com/Erne1357/portfolio)** | The site behind this profile — bilingual, API-driven, behind Nginx with Let's Encrypt. | React · TypeScript · Vite · FastAPI · Docker |

---

## On the monitoring side

This is the part a repo list doesn't show, so here it is:

- **Metrics inside the app, not only on the host.** Requests and error rate per app, the routes
  with the worst p95, and saturation signals that say which pool is full — threadpools, database
  pool, event-loop lag — instead of a CPU graph that only says something is slow.
- **Traces with sampling that admits what it drops.** The slow and the failed traces are kept
  plus a small baseline of the rest; the decision windows are written down, so a *trace not
  found* reads as expected and not as an outage.
- **Logs and traces that point at each other.** `trace_id` goes into the JSON logs, so Loki jumps
  to Tempo and back. Async tasks are their own traces, linked to the request that queued them.
- **Alerts that are tested.** The Prometheus rules have unit tests, the dashboards are checked in
  CI, and the deploy runs preflight, apply and smoke tests, rolling back on its own if smoke
  fails.
- **Nothing published.** Agents push over a private network; the stack binds to localhost and you
  reach it over an SSH tunnel instead of putting one more Grafana on the internet.

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

**Monitoring & DevOps**
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

Two ICPC Mexico Finals in a row and back-to-back state titles. I compete in C++ and ship in
Python.

---

## Education & certifications

- **B.S. in Computer Systems Engineering** — ITCJ, 2021–2025 (graduated)
- **Technical Diploma in Programming** — CBTIS 114, 2018–2021
- **CCNAv7: Introduction to Networks** — Cisco Networking Academy, 2024

---

<sub>Programming since 2018 · Open to backend, platform and DevOps/SRE roles · Spanish (native) · English (professional)</sub>
