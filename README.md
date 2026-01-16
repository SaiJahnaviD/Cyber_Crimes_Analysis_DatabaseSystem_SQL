# 🥷🛡️ Digital Forensics & Cybersecurity Database System - SQL 

A comprehensive relational database project designed to support cyber‑incident investigation, digital forensics operations, analyst resource management, and regulatory compliance tracking.

---

## 📌 Project Overview

The **Digital Forensics & Cybersecurity Database System** is a structured, normalized relational database that models the real‑world operations of cybersecurity firms, law‑enforcement agencies, and security operations centers (SOCs).

It enables organizations to:

* Track cyber threats and incidents
* Manage digital evidence and forensic tools
* Assign and monitor analyst responsibilities
* Record analyst training and specialization
* Support multi‑agency collaboration
* Enforce and audit regulatory compliance (GDPR, HIPAA, ISO 27001, etc.)

The project emphasizes **data integrity, traceability, auditability, and scalability**, ensuring that investigations remain legally defensible and operationally efficient.

---

## 🎯 Objectives

* Design a fully normalized (3NF) cybersecurity investigation database
* Model complex many‑to‑many operational relationships using bridge tables
* Support forensic workflows with timestamped evidence and tool usage
* Track compliance against multiple regulatory frameworks
* Enable analyst skill management and specialization tracking
* Provide a foundation for future automation and AI‑driven analytics

---

## 🧱 System Architecture

The system is built around the following core domains:

| Domain              | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| Threat Intelligence | Catalogs known cyber threats and their attack patterns       |
| Incident Management | Records security incidents and resolution status             |
| Digital Forensics   | Stores evidence, integrity hashes, and tool analysis history |
| Human Resources     | Tracks analysts, roles, experience, and training             |
| Compliance          | Maps incidents to regulatory requirements and audit results  |
| Collaboration       | Manages external agency partnerships                         |

---

## 🗂️ Core Entities

* **THREAT** – Known cyber threats and severity levels
* **INCIDENT** – Individual cyber incidents linked to threats
* **EVIDENCE** – Digital artifacts collected per incident
* **ANALYST** – Cybersecurity professionals handling investigations
* **TOOL** – Forensic tools used during analysis
* **TOOL_TYPE** – Categories of forensic tools
* **TRAINING** – Professional development programs
* **PARTNERSHIP** – External agencies and collaborators
* **REGULATION** – Compliance frameworks
* **REGULATORY_COMPLIANCE** – Audit results per incident
* **ATTACK_PATTERN** – Threat behavior and mitigation strategies

---

## 🔗 Bridge (Junction) Tables

These tables resolve many‑to‑many relationships and preserve audit trails:

* `ANALYST_TOOL` – Tools used by analysts + last usage date
* `EVIDENCE_TOOL` – Tools used to analyze evidence + timestamp
* `INCIDENT_ASSIGNMENT` – Analysts assigned to incidents + role & date
* `INCIDENT_PARTNERSHIP` – Partnerships involved in incidents + collaboration level
* `ANALYST_TRAINING_ATTENDANCE` – Training participation + completion status
* `FORENSIC_SPECIALIST` – Analyst subtype with certifications and lab access

---

## 📐 Entity‑Relationship Model Highlights

* One threat → many incidents
* One incident → many evidence records
* Many analysts ↔ many incidents
* Many analysts ↔ many tools
* Many tools ↔ many evidence items
* Many incidents ↔ many partnerships
* One incident → many compliance checks
* One analyst → optional forensic specialization

The ER diagram enforces:

* Referential integrity via foreign keys
* Mandatory attributes for audit‑critical data
* Controlled cardinalities and participation constraints

---

## 📏 Normalization

The schema follows strict normalization standards:

* **0NF → 1NF**: Eliminated repeating groups and multi‑valued fields
* **1NF → 2NF**: Removed partial dependencies from composite keys
* **2NF → 3NF**: Eliminated transitive dependencies

Benefits:

* No redundant data storage
* Reduced update anomalies
* High data consistency
* Improved scalability

---

## 🧪 Sample Supported Queries

* Unresolved incidents report
* Incidents by threat severity
* Analyst experience comparison
* Evidence analyzed using specific tools
* Compliance audit history per incident
* Analyst training completion tracking

---

## 🔐 Data Integrity & Security Features

* Primary & foreign key enforcement
* Cryptographic hashes for evidence verification
* Timestamped forensic activity logs
* Mandatory compliance status and audit dates
* Controlled ENUM values for severity, status, and collaboration levels

Placeholder values (e.g., *Unknown Threat*, *Former Analyst*) are used instead of NULLs to preserve historical integrity.

---

## 🚀 Future Enhancements

* AI‑based threat prediction models
* Automated compliance reporting dashboards
* Real‑time incident ingestion pipelines
* Integration with SIEM platforms
* Role‑based access control (RBAC)
* Blockchain‑based evidence integrity verification

---

## 🛠️ Technologies & Concepts Used

* Relational Database Design
* Entity‑Relationship Modeling (ERD)
* SQL (DDL & DML)
* Database Normalization (1NF–3NF)
* Cybersecurity domain modeling
* Digital forensics workflow design

---

## 📁 Repository Contents

```
/diagrams        → ER diagrams & schema design files
/sql             → Table creation scripts & sample queries
/docs            → Data dictionary & project documentation
/database        → Microsoft Access database file (.accdb)
README.md        → Project overview
```

---

## 👥 Intended Users

* Cybersecurity analysts
* Digital forensic investigators
* Security operations teams
* Compliance officers
* Database designers
* Academic researchers

---
