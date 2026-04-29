# Tong Liu

catongliu@gmail.com | 302-290-3698 | San Mateo, CA

---

## CAREER SUMMARY

Data professional specializing in data engineering, experimentation infrastructure, and analytics across technology, finance, and digital advertising. Most recently building large-scale holdout measurement systems at Meta for a flagship consumer app with billions of users. Skilled in managing the entire end-to-end analytical cycle, from data ingestion and pipeline orchestration to visualization and insights. A scientist in approach and an engineer in execution — author of 4 internal AI agents, ~95 PRs shipped in 10 months at Meta, and a track record of driving cross-organizational alignment between product and platform teams.

---

## SKILLS

- **Programming & DevOps**: SQL, Python, Java, R, Git, Terraform, Agile (JIRA)
- **Databases**: MySQL, SQL Server, Amazon Redshift, GCP BigQuery, MongoDB, AWS DynamoDB, Snowflake, Sharded Relational Databases
- **Data Processing & Big Data**: dbt, Apache Airflow, Apache Spark, Hive, Presto/Trino, Production Data Orchestration Frameworks
- **Cloud Platforms**: AWS (S3, RDS, Lambda, EC2, Glue), GCP (GCS, Dataform), Databricks, Microsoft Fabric
- **Experimentation**: Long-term Holdout Measurement, A/B Testing, Metric Materialization & Pre-Computation, Experiment Metadata Schemas, Subpopulation Analysis
- **AI & Tooling**: AI Coding-Assistant Agent Authoring, Structured Context Engineering (AGENTS.md), Parameterized Pipeline Testing
- **Data Science**: Statistics, Metrics Design, Root Cause Analysis, Tableau, Power BI, Machine Learning

---

## WORKING EXPERIENCE

### Meta | Data Engineer | 2025 – Present · Menlo Park, CA

*Experimentation Infrastructure & Long-Term Holdout Measurement — ~95 PRs · 4 AI Agents · B+ Users Reached*

- Designed and shipped a multi-stage production pipeline aggregating long-term holdout experiment results — from raw statistics through creator-cohort segmentation and subpopulation breakouts (country, region, age) — into a single product-contribution table consumed by leadership dashboards, powering reporting on a flagship app with **billions of users**
- Sole maintainer of the metadata schema cataloging every long-term holdout experiment for a major consumer app — active state, organizational rollups, dilution factors, reporting periods. Drove migration onto a platform-wide canonical data model via schema evolution across sharded relational databases with **zero historical data loss**; secured commitment to onboard **80% of next half's holdouts** onto the unified product
- Led the **first-ever shared engineering goal** between the app's measurement team and Meta's central experimentation platform team on holdout management; closed a **multi-year discontinuity** in how holdout metadata flows between product and platform through field-by-field mapping analysis and abstraction-layer design
- Authored an interactive Python notebook tool integrated with the experimentation platform's metric scheduling API for programmatic pre-computation of experiment metrics; adopted across the measurement organization to monitor compute-quota usage across **multiple consumer apps**
- Built **4 AI coding-assistant agents** automating recurring data-engineering workflows: new-metric onboarding, bulk metric backfill, experiment-metric scheduling, and parameterized pipeline testing — codifying institutional knowledge accessible to both new team members and AI assistants
- Owned the front-end dashboard for a generative-AI product's experiment reporting — methodology AI assistant, cohort-level filtering, statistical-significance presentation — enabling experimenters to interpret results **without writing queries**

### Intuit | Business Intelligence Analyst, Contractor | May 2025 – Present · Mountain View, CA

- Built an automated sales dashboard for QuickBooks Enterprise Solutions (Intuit's highest-revenue product), integrating data across Sales, Product, and Marketing via Tableau and AWS Glue; cut manual processing from ~1 hour to seconds
- Identified and escalated 3+ critical data issues in the data mart, helping reduce weekly funnel discrepancies by 20% through upstream diagnostics and cross-functional coordination
- Delivered weekly commentary on QuickBooks Enterprise funnel metrics to Sales and Data Science leaders; partnered with Sales and Finance to align forecasts and explain variances, improving visibility and alignment

### Blueprint Technologies | Data Engineer, Contractor | Feb 2024 – Aug 2024 · Remote, CA

- Facilitated the transformation from ETL to ELT for a leading digital provider; migrated 245 tables from Redshift to GCP BigQuery; enhanced data freshness from 45 minutes to 5 minutes along with 30+ data pipelines using GCP
- Developed an automated PySpark data validation framework to ensure the integrity of billions of records in migration
- Optimized BigQuery costs by 20% through implementing partitioning, query tuning, and efficient scheduling windows
- Crafted real-time GCP alerts if pipeline errors occur, reducing response times by 10% and improving overall issue resolution efficiency

### LendingClub | Senior Data Analyst, Credit & Fraud Risk | Jun 2022 – Nov 2023 · San Francisco, CA

- Designed and automated data pipeline in Airflow, SQL (Hive, Trino), and Git to streamline data preparation, reducing manual effort by 60% and increasing data consistency by 10%
- Automated simulation process using Python to enhance the audit process, cutting manual audit time by 70%
- Created dynamic Tableau dashboards to automate the assessment of the overall portfolio by segmentation
- A/B tested early performance on new verification strategies, decreased default-prone conversion rate by 40%

### American Credit Acceptance | Data Analyst, Pricing Strategy | Mar 2021 – Jun 2022 · Spartanburg, SC

- Built a visualization dashboard for car loan business funnels (application, decision, contract, and customer profile) from end to end in Tableau to provide pricing insights for executives
- Implemented A/B Tests on new pricing levers increasing 2% ROI; collaborated with the Engineering team to manage pricing production code for a $5-billion loan portfolio using Git and Agile methodologies
- Developed a new conversion model using XGBoost for internal financial projection with the Modeling team, increasing AUC score from 59% to 85%

---

## EDUCATION

**Carnegie Mellon University** — M.S. in Information Systems Management · 2020

**University of Delaware** — B.S. in Mathematics and Economics · 2018
