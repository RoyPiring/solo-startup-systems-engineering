---
nextwork_uuid: eb97ffca-4cde-41b0-9507-4765d762c83c
original_filename: legendary-eb97ffca-4cde-41b0-9507-4765d762c83c.md
migrated_to: advisor-smb-engineering/smb-prospect-warehouse.md
migrated_at: 2026-05-04
schema: nextwork-generator
final_migrated_at: 2026-05-04
final_migrated_from: advisor-smb-engineering/smb-prospect-warehouse.md
final_migrated_to: startup-systems-engineering/smb-prospect-warehouse.md
---

<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build an SMB Prospect Warehouse

**Project Link:** [View Project](https://learn.nextwork.org/projects/eb97ffca-4cde-41b0-9507-4765d762c83c)

**Author:** Roy Piring Jr  
**Email:** rpiringhawaii@gmail.com

---

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/eb97ffca-4cde-41b0-9507-4765d762c83c_pidhe1dy)

## Building a Schema-First Prospect Intelligence System

### Project vision and motivation

This project builds a local prospect intelligence warehouse designed to identify and prioritize high-value SMB clients in the Austin market.

The system is structured around a schema-first approach, where data contracts are defined before ingestion. Claude is used as an enrichment engine, while DuckDB serves as the analytical storage layer. The goal is to simulate a production-ready pipeline that can generate, filter, enrich, validate, and surface prospect data for decision-making.

### Environment setup goals

The environment establishes a controlled execution layer for the pipeline.

A dedicated virtual environment is created to isolate dependencies and ensure consistent runtime behavior. Required Python packages are installed, and Claude Code connectivity is verified to enable downstream enrichment workflows. This setup ensures that all components operate without conflict and can be reproduced across environments.

### Why virtual environments matter

Virtual environments enforce dependency isolation and reproducibility.

They prevent conflicts between system packages and project-specific libraries while ensuring consistent execution across development and deployment. Removing the environment fully cleans the project without affecting the global system.

## Verifying Claude Code and the Development Environment

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/eb97ffca-4cde-41b0-9507-4765d762c83c_syv2kmza)

## Designing the 12-Field Pydantic Schema with Claude Desktop

### Schema design approach

The system begins with defining a strict schema using a Pydantic v2 model.

The ProspectSignal model enforces structure across fields such as company identity, location, industry classification, employee size, revenue band, and scoring signals. Each field includes constraints such as regex patterns, enums, and length validation to ensure data consistency.

### Why schema-first design matters

The schema acts as the contract for the entire pipeline.

Every component, including generation, enrichment, and export, adheres to the same structure. This prevents malformed data from propagating and simplifies prompt design by allowing exact field references instead of ambiguous descriptions.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/eb97ffca-4cde-41b0-9507-4765d762c83c_srqtpmdq)

## Generating the 55,000-Row Austin SMB Universe

### Universe generation strategy

A synthetic dataset of 55,000 SMB records is generated and stored in DuckDB.

The dataset uses realistic Austin zip codes, NAICS classifications, and weighted distributions to approximate real-world business characteristics. This establishes a production-scale dataset for testing the pipeline.

### The value of a realistic synthetic dataset

Operating at scale surfaces issues early.

A large dataset exposes performance bottlenecks, filtering inefficiencies, and query limitations that would not appear in small test datasets. Sampling from this dataset mimics real CRM workflows where subsets are selected for processing.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/eb97ffca-4cde-41b0-9507-4765d762c83c_jb7xojib)

## Applying the ICP Funnel to Surface the Top 25 Prospects

### ICP filtering strategy

The dataset is reduced using an Ideal Customer Profile filter.

Industry, employee size, and geography are applied to narrow the dataset from 55,000 records to a smaller candidate pool. From this pool, the top 25 prospects are selected for enrichment.

### Why filtering and scoring work together

Filtering removes low-fit candidates, while scoring ranks viable ones.

The confidence score introduces prioritization, allowing the system to focus on high-probability prospects. This creates a two-stage funnel where cheap filtering is followed by more expensive evaluation.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/eb97ffca-4cde-41b0-9507-4765d762c83c_sx4u192q)

## Enriching Prospects with Claude Code's Headless Retry Loop

### How Claude Code powers the extraction engine

Claude Code is used to enrich selected prospects with structured data.

A headless Python loop processes each record and validates output against the schema. If validation fails, the error is fed back into the prompt and retried automatically, enabling self-correction without manual intervention.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/eb97ffca-4cde-41b0-9507-4765d762c83c_trm5nvmu)

### Inspecting a validated prospect record

Validated records confirm the pipeline is functioning correctly.

An example record shows a company with an employee band of 11–50 and a confidence score of 0.74, demonstrating that enrichment outputs align with schema constraints and scoring logic.

## Loading the Warehouse, Certifying Data Quality, and Launching the Dashboard

### End-to-end pipeline completion

Validated records are loaded into DuckDB and exported as Parquet.

Great Expectations runs data-quality checks across the dataset and generates an HTML report. A Streamlit dashboard is then launched to visualize funnel metrics, revenue projections, and prospect details.

### Two-layer validation: Pydantic vs Great Expectations

Validation occurs at both record and dataset levels.

Pydantic enforces structure during ingestion, ensuring each record meets schema requirements. Great Expectations evaluates the dataset as a whole, identifying distribution issues, null values, and consistency problems.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/eb97ffca-4cde-41b0-9507-4765d762c83c_i1x8yaod)

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/eb97ffca-4cde-41b0-9507-4765d762c83c_pidhe1dy)

## Adding a Monday Refresh with Staleness Detection

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/eb97ffca-4cde-41b0-9507-4765d762c83c_kx9f09ql)

### Diff-and-update vs full overwrite

The system updates only changed records.

This preserves historical data and enables tracking of changes over time. Full overwrites would remove this visibility and eliminate the ability to detect updates between runs.

## Reflections and Key Takeaways

### Tools and concepts mastered

This project uses DuckDB, Great Expectations, Streamlit, Pydantic, NumPy, and Claude Code to build a full data pipeline.

It demonstrates schema-first design, synthetic data generation, ICP filtering, AI-driven enrichment, validation layers, and dashboard-based analytics within a single system.

### Time and challenges

This project took about 1 hour. The main challenge was ensuring the environment and Claude integration were correctly configured before pipeline execution.

### Looking ahead

This project shows how to build a local prospect intelligence system with production-style patterns.

The next step is integrating external data sources and scaling enrichment workflows to operate continuously within a real sales pipeline.

---

*Built with [NextWork](https://learn.nextwork.org) - [View this project](https://learn.nextwork.org/projects/eb97ffca-4cde-41b0-9507-4765d762c83c)*
