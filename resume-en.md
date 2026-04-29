# TONG LIU

**Data Engineer**

---

## SUMMARY

Data Engineer at Meta building large-scale experimentation infrastructure and long-term holdout measurement systems for a flagship consumer app with billions of users. ~95 PRs shipped in 10 months. Owns end-to-end production data pipelines, critical metadata schemas, and cross-organizational alignment initiatives. Author of 4 internal AI agents that automate data-engineering workflows. Combines deep pipeline engineering with platform-level thinking — progressing from individual contributor to cross-team technical lead within three quarters.

**Core stack**: Python · SQL (Hive/Presto) · Production Data Orchestration · Sharded Relational Databases · Dynamic Configuration Management · Distributed Query Engines · AI Agent Development

---

## EXPERIENCE

### Data Engineer — Meta · 2025 – Present

*Experimentation Infrastructure & Long-Term Holdout Measurement*

#### Production Pipeline for Holdout Measurement

- Designed and shipped a multi-stage production pipeline aggregating long-term holdout experiment results — from raw statistics through creator-cohort segmentation and subpopulation breakouts (country, region, age) — into a single product-contribution table consumed by leadership dashboards
- Powers reporting for a flagship app with **billions of users**; outputs feed top-priority dashboards reviewed by app leadership
- Delivered via 6 dependent PRs over a quarter using **Python orchestration, Hive/Presto distributed SQL**, and backfill automation
- Recovered correctness on previously incorrect topline values; eliminated duplicate rows from rebalanced-experiment edge cases; established a reusable pipeline pattern (overall → archive → demotion → subpopulation → metrics expansion) the team continues to apply

#### Holdout Experiment Metadata Schema Ownership

- Sole maintainer of the schema cataloging every long-term holdout experiment for a major consumer app — active state, organizational rollups, dilution factors, reporting periods
- Drove migration onto a platform-wide canonical data model via **schema evolution across sharded relational databases and dynamic configuration management systems**; resolved type-conflict migration in production with **zero historical data loss**
- Enabled new fields (rebalanced date, holdout-use-case taxonomy, metric IDs, subpopulation metric IDs) to flow end-to-end; secured commitment to onboard **80% of next half's app-level holdouts** onto the unified product

#### Cross-Organizational Data-Parity Initiative

- Led the **first-ever shared engineering goal** between the app's measurement team and Meta's central experimentation platform team on holdout management
- Conducted field-by-field mapping between legacy app schema and canonical model; designed abstraction-layer proposals across multiple working sessions
- Closed a **multi-year discontinuity** in how holdout metadata flows between product and platform; outcome shapes how experiments are configured, stored, and reported going forward

#### Bulk Scheduling Tooling for Metric Pre-Computation

- Authored an interactive **Python notebook tool** integrated with the experimentation platform's metric scheduling API, supporting arbitrary subpopulation slicing and rollup-window selection
- Adopted across the measurement organization to monitor compute-quota usage across **multiple consumer apps**
- Replaced manual per-experiment scheduling with a scriptable bulk path; enabled dimensional analysis (sub-country, age cohort) the prior workflow could not support at scale

#### AI Agents for Data-Engineering Automation

- Built **4 AI coding-assistant agents** automating recurring workflows: new-metric onboarding, bulk metric backfill, experiment-metric scheduling, and parameterized pipeline testing
- Authored on a major **AI coding-assistant platform** with structured agent context files checked into the repository, codifying institutional knowledge for both new team members and AI assistants
- Lowered onboarding cost for new measurement metrics and shifted team from individual-pipeline ownership toward platform-style tooling

#### Generative-AI Experiment Dashboard

- Owned the front-end dashboard for a generative-AI product's experiment reporting — methodology AI assistant, cohort-level filtering, statistical-significance presentation, per-cohort drill-down
- Built with **internal web application framework**, integrated with experimentation analysis platform API, optimized via stale-while-revalidate caching
- Delivered a single dashboard surface enabling experimenters to interpret gen-AI results **without writing queries**

---

## TECHNICAL SKILLS

| Category | Technologies |
|---|---|
| **Languages** | Python (production pipelines, automation, AI agent skills), SQL (Hive/Presto — analytics-grade query optimization, CTE refactoring) |
| **Data Infrastructure** | Distributed SQL query engines (Hive, Presto), production data orchestration frameworks, backfill automation, pipeline SLA management |
| **Databases & Storage** | Sharded relational databases, dynamic configuration management systems, distributed version control |
| **Experimentation** | Long-term holdout measurement, A/B testing infrastructure, metric materialization & pre-computation, experiment metadata schemas, subpopulation analysis |
| **AI & Tooling** | AI coding-assistant agent authoring, structured context engineering (AGENTS.md / skill files), parameterized pipeline testing |
| **Analytics & Reporting** | Real-time analytics platforms, interactive notebook environments, internal web application frameworks, dashboard development |
| **Practices** | Cross-functional alignment (product × platform), data quality & correctness validation, schema migration & evolution, on-call ownership |

---

## GROWTH TRAJECTORY

Three quarters, three modes — from executor → owner → platform thinker:

| Quarter | Mode | What Happened |
|---|---|---|
| **Q1** | Foundations | Pipeline fundamentals + data-quality guardrails on session-measurement pipelines |
| **Q2** | Ownership | Took full ownership of holdout production pipeline + metadata schema — shipped 6-PR build while absorbing on-call |
| **Q3** | Platform Mindset | Led cross-org data-parity alignment, shipped gen-AI dashboard, authored AI agents — shifted from building pipelines to building systems that build pipelines |

---

## EDUCATION

[University Name] — [Degree], [Field] · [Year]
