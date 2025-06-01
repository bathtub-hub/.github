# bathtub-hub 🛁🐥

_Empowering researchers and industry in Brazil's energy and climate sectors by integrating, standardizing, and simplifying access to complex, multi-source data._

---

## 📖 Introduction

Gathering reliable and standardized energy and climate data in Brazil is notoriously challenging. Data is fragmented across numerous providers, each using unique formats and interfaces, causing significant delays and complexity for researchers, data scientists, and industry stakeholders.

**`bathtub-hub`** tackles this issue head-on by integrating multiple data sources and providing structured, validated, and ready-to-use datasets.

---

## 🎯 Project Goals

- Integrate diverse sources of energy, climate, rainfall, and wind data.
- Standardize data into structured, reliable, and performant formats.
- Provide clear, consistent, and intuitive datasets for analytical and operational usage.
- Enable quick and trustworthy analytics, machine learning models, and research initiatives.

---

## 🧱 Architecture Overview

We use a structured, layered data lake approach on AWS S3, leveraging modern cloud-native tools:

### 📂 Data Lake Layers:

- **Bronze (`bronze/`)**: Raw data, provider-specific.
- **Silver (`silver/`)**: Cleaned, normalized data stored as Iceberg tables, provider-specific.
- **Gold (`gold/`)**: Curated, aggregated, and enriched data, domain-specific.

### ☁️ AWS Cloud Components:

- **Storage**: Multiple AWS S3 buckets (bronze, silver, gold).
- **Catalog**: AWS Glue Data Catalog.
- **Tables**: Apache Iceberg tables managed through AWS Athena.
- **Processing**: Airflow, EMR, AWS Glue, Step Functions, Lambda, EC2.

---

## 📌 Repository Structure

The **bathtub-hub** organization is divided into modular repositories for better maintainability and scalability:

| Repo Name                    | Description                                                   |
| ---------------------------- | ------------------------------------------------------------- |
| **[`infra`](#)**             | Infrastructure-as-code (Terraform modules, AWS resources).    |
| **[`catalog`](#)**           | Dataset metadata, schema contracts, validation rules.         |
| **[`pipelines-core`](#)**    | Core reusable libraries (ETL logic, schema validators).       |
| **[`ingest-<provider>`](#)** | Provider-specific ingestion logic (ONS, ANEEL, INMET, etc.).  |
| **[`jobs-curated`](#)**      | Domain-specific transformations (energy, climate, forecasts). |

Each repository includes its own documentation (`README.md`) covering:

- Installation instructions
- Usage examples
- Contribution guidelines
- Architecture and data schema details

---

## 🚧 Contributing

We warmly welcome community and industry contributions! Here’s how you can get involved:

### 🛠 Types of Contributions:

- **Integration pipelines** for new data sources (following enforced standards).
- **Analytical datasets** creation, including aggregated datasets or predictive model datasets.
- **ML Models** training, validation, and integration.
- **Documentation improvements** (clear, concise, useful docs are highly valued).

### ✅ Contribution Standards:

- **Integration**:

  - Iceberg tables
  - AWS Glue Catalog integration
  - Layered architecture (`bronze/`, `silver/`, `gold/`)
  - Specific naming conventions
  - CI/CD pipelines for automated deployments and validation

- **Analytical/Operational**:
  - Naming and S3 organization standards must be respected
  - Must pass data and model validations, as well as peer review processes
  - Create clear, thorough documentation describing data and transformations

### 🛎 How to Contribute:

1. Fork the relevant repository.
2. Create a new feature branch (`feature/<your-feature-name>`).
3. Implement your integration or analytical dataset following provided standards.
4. Submit a Pull Request (PR) clearly describing your changes.

---

## 🐞 Issues and Feature Requests

- **Clearly title** your issues (e.g., `[Bug]`, `[Feature]`, `[Improvement]`).
- Use provided **GitHub issue templates** for clarity.
- Assign appropriate **labels** (`bug`, `enhancement`, `help wanted`, etc.).
- Tag **maintainers** and link relevant PRs to issues.
- For commercial usage or feature requests outside our standard license, use the label `commercial-request`.

---

## 🚀 Local Development & Testing

- Contributors can develop integrations locally, even without direct AWS access.
- Minimal PR structure: extraction scripts (`bronze`), normalization (`silver`), schema files, basic tests.
- Submit PR; maintainers assist in adapting and deploying to AWS environments.

---

## 📝 Licensing

**Bathtub-hub** content is provided under the terms of the:

[**Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)**](https://creativecommons.org/licenses/by-nc-nd/4.0/).

You are free to:

- **Share** — copy and redistribute the material.
- **Use** — access and analyze data for research and studies.

Under the following terms:

- **Attribution** — Explicitly cite "bathtub-hub" and provide a link to the source repository.
- **NonCommercial** — You may not use the material for commercial purposes.
- **NoDerivatives** — You may not remix, transform, or build upon the material without explicit permission.

⚠️ **Commercial use** (tools, automations, data-based products) **is strictly prohibited without explicit written permission** from the maintainers.

📩 For commercial licensing requests, please contact:  
`[your-email@example.com]`

---

## 📫 Contact & Community

- Open a GitHub Issue for general inquiries or support requests.
- Join our community discussions (Slack or Discord link if applicable).

---

🎉 **Welcome aboard!** 🎉

Together, let’s simplify data access and empower research and innovation in the Brazilian energy and climate sectors.

_Happy data bathing!_ 🛁🌊
