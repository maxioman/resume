# OCBC Bank (Singapore) — Basel II RWA Data Warehouse & Extraction Architecture (2005 – 2007)

## Project Overview
- **Client:** OCBC Bank Group (Singapore, Malaysia, and International Affiliates)
- **Role:** Senior Technical Consultant – BASEL II Extraction & Scheduling Lead (Contracted via DL Resources)
- **Team Managed:** Extraction Team (2), Unix & Control-M Team (2), Vendor ETL Teams (10)
- **Environment:** Teradata (MultiLoad, FastLoad, TPump), NCR Financial Services Logical Data Model (FSLDM), BMC Control-M, DataStage, Synopsis, C++, Unix Shell Scripting, Connect:Direct (C:D) over SSH

## Business Challenge
- OCBC Bank Group was mandated to comply with the Basel II Capital Adequacy Framework (AIRB approach) across Singapore, Malaysia, and international entities.
- The bank embarked on a major initiative to implement a centralized Risk-Weighted Assets (RWA) calculation engine and regulatory data warehouse.
- **The Core Conflict:** The bank already operated an Enterprise Data Warehouse (AMP). The massive new Basel II extraction workloads risked colliding with daily business-as-usual (BAU) warehouse processing and missing critical regulatory cut-off windows.

## Architectural Guiding Principles & Solutions
1. **Decoupled Load & Transform Architecture:**
   - Designed a robust control framework decoupling extraction from Load/Transform (L/T).
   - Enabled multi-day catch-up processing without stalling daily transactional extractions.
2. **Unified Scheduling & Dependency Matrix:**
   - Unified the legacy AMP warehouse schedule and the new Basel II ETL pipelines into a single master schedule governed by BMC Control-M.
3. **High-Throughput Parallel Ingestion:**
   - Engineered extraction scripts utilizing Teradata MultiLoad, FastLoad, and TPump, optimizing throughput from legacy source cores into the NCR FSLDM data warehouse.
4. **Upstream Data Mart Feeds:**
   - Built automated ETL job schedules supplying credit exposure data to upstream analytical engines: SAS for Credit Risk Rating models and Fermat for Central Regulatory Capital calculation.
5. **Rollout & Fallback Design:**
   - Designed a phased cutover framework allowing dual parallel runs with fallback capabilities to guarantee business continuity.

## Business Impact & Outcomes
- Successfully delivered on-time regulatory compliance for OCBC Group under Basel II AIRB standards.
- Reduced overall ETL batch processing window, eliminating schedule variance and resource contention across the enterprise warehouse.
