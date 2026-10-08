# Standard Chartered Bank (SCB) & Scope International — Master Project Case Studies (1998 – 2005)

## 1. Single Customer Identifier (SCI 2.0) & Central Credit Limit Management
- **Role:** Product Manager & Technical Architect (Team Managed: ISC 4, TCS 100+, HCL 20+)
- **Environment:** AIX, Oracle, Tomcat, Apache, IBM MQ Series, ISIS Middleware, XML Pub/Sub
- **Business Challenge:**
  - SCI Release 1.0 (hosted in the UK data center) suffered from limited regional reach due to a heavy applet architecture, causing latency and adoption barriers across Asian and African branches.
  - The bank needed a high-performance central repository of standard codes, Legal Entity customer identities, credit grades, and real-time credit limits.
- **Architectural Solution:**
  - Architected SCI 2.0 with a lightweight thin-client web architecture accessible from global processing hubs and regional spokes.
  - Designed an event-driven publish/subscribe application integration layer using XML over MQ Series (ISIS middleware), synchronizing customer limits and exposures with participating transaction engines: eBBS (Core Banking), Hogan (Cash Systems), IMEX (Trade Finance), and Basel II Helios Data Warehouse.
  - Multi-tier limit hierarchy: governed limits across ECAI sovereign/parent group, customer entity, facility, and sub-line levels.
  - Formulated stress/volume test strategies for HTTP throughput and background XML processing resilience, tuning AIX, Tomcat, Oracle, and network parameters.
- **Outcome:** Global single customer view and centralized credit risk exposure monitoring adopted across international franchises.

---

## 2. Multi-Business Platform (MBP) Clustered Enterprise Architecture & Upgrade
- **Role:** Technical Architect & Product Manager (MBP Team: 10 engineers + vendors)
- **Environment:** Clustered AIX Hardware, IBM WebSphere Application Server (WAS 4.0 to 5.0), IBM Content Manager, MQ Workflow (4.0 to 4.1), MQ Series (3.0 to 4.0), Network Dispatcher, Policy Director, HACMP
- **Business Challenge:**
  - MBP served as the bank's mission-critical scan, print, and process-driven workflow engine across front-office, middle-office, and back-office hubs.
  - Required upgrading foundational middleware without disrupting high-volume message feeds from host payment systems (Hogan) and trade systems (IMEX).
- **Architectural Solution:**
  - Designed a high-availability clustered architecture using IBM Network Dispatcher and WAS Model/Clone instances with HACMP failover.
  - Executed a phased upgrade path maintaining backward compatibility between mixed software versions.
  - Tested resilience under severe transaction stress from Hogan and IMEX, ensuring scan-and-print SLAs remained uncompromised.
- **Outcome:** Seamless zero-downtime middleware upgrade powering shared-services operations across multiple countries.

---

## 3. Project Cocteau: Centrally Hubbed Multitenant Custody Architecture (Atos HK)
- **Role:** Product Manager & Implementation Lead
- **Environment:** Atos Hong Kong Data Center, New Custody System (NCS), Sybase, CICS TxSeries, Macro 4 Columbus
- **Business Challenge:**
  - Global Securities Services operated fragmented, distributed country deployments of the NCS custody system, resulting in escalating operational costs and inconsistent service delivery.
- **Architectural Solution:**
  - Engineered a centralized multitenant deployment framework for NCS within the Atos Hong Kong Data Center.
  - Centralized operational execution and batch processing into a shared-services hub while strictly preserving local entity regulatory ownership, approval authority, and local central bank compliance.
  - Recoded mainframe interface programs using IBM SNA API to support parameterized profiles stored in relational databases.
  - Implemented centralized remote printing and archival using Macro 4 Columbus utilities.
- **Outcome:** Dramatic operational expense reduction and established the operational blueprint for SCB's hub-and-spoke custody processing.

---

## 4. Japan Production Server Performance Rescue (J50 to H80 Hardware Reconfiguration)
- **Role:** SCB Lead Systems Analyst & Technical Architect (Tiger Team Leader with IBM and Sybase)
- **Environment:** IBM RS6000 (J50 to H80 upgrade), AIX, Sybase ASE 11.9.2, CICS TxSeries, Encina SFS
- **Business Challenge:**
  - Following a hardware upgrade from J50 to H80 in the Japan Securities Services production environment, the system experienced acute performance degradation.
  - Nightly batch execution times doubled, routinely slipping past the morning market cut-off window.
- **Architectural Solution:**
  - Formed a specialized "hot pursuit" task force partnering directly with senior lab engineers from IBM and Sybase.
  - Created an exact replica environment at IBM labs to conduct deep telemetry probing into AIX kernel parameters, Sybase ASE buffer caches, lock schemes, and CICS region configurations.
  - Prioritized and methodically stress-tested combinations of operating system and database configuration parameters.
- **Outcome:**
  - Achieved a **200%+ performance gain on batch job execution timings**, bringing nightly batches comfortably inside regulatory SLA windows.
  - Improved online transaction response times for critical settlement and clearing functions by **60%**.
  - Received a special award and formal commendation from the Japan Securities Services Head and IT Head.

---

## 5. Mid-Range Infrastructure Consolidation Project
- **Role:** Systems Analyst & Technical Architect
- **Environment:** AIX Workload Manager (WLM), TxSeries 4.3, Sybase 12.0, TCP/IP Encapsulation, SEMA Datacenters (SG, MY, HK)
- **Business Challenge:**
  - Decommission country-level distributed mid-range servers across Singapore, Malaysia, and Hong Kong into consolidated data center infrastructure.
- **Architectural Solution:**
  - Verified application resilience in shared Workload Manager (WLM) environments.
  - Conducted comprehensive impact analysis for TxSeries 4.3 and Sybase 12.0 upgrades.
  - Migrated legacy SNA/LLC host communications to TCP/IP packet encapsulation.
- **Outcome:** Simplified datacenter footprint, meeting the Bank’s Technical Architecture and Standards (TAS) guidelines.

---

## 6. NCS Version 3 Upgrade & SWIFT 98/2000 Compliance
- **Role:** Systems Analyst & Lead Technical Designer
- **Environment:** AIX, C++ 3.1.0, Sybase 11.9.2, TxSeries 4.3, Encina SFS, DCE 2.2, SWIFT
- **Business Challenge:**
  - Mandatory global SWIFT 98/2000 regulatory standards update requiring fundamental tag modifications and STP logic updates.
- **Architectural Solution:**
  - Managed Sybase (11.0.3 to 11.9.2) and TxSeries (4.2 to 4.3) upgrade paths.
  - Refactored C++ and PowerBuilder application modules to handle revised SWIFT message structures.
  - Tuned Straight-Through Processing (STP) queues, background GL and charges generation, and online trade affirmation response times under high transaction volume.
- **Outcome:** 100% on-time compliance with global SWIFT standards without disruption to daily trade settlements.

---

## 7. NCS Country Implementations (SCB Taiwan & Indonesia)
- **Role:** Implementation Systems Analyst
- **Environment:** IBM RS6000, AIX, Sybase, CICS TxSeries, BMC Control-M, STORQM
- **Business Challenge:**
  - Greenfield rollout of Standard Chartered's New Custody System (NCS) to Indonesia and Taiwan franchises.
- **Architectural Solution:**
  - Commissioned RS6000 server environments, Sybase databases, and CICS transactional regions.
  - Built interfaces to host banking systems: Hogan (Cash), MSA (General Ledger), and GAMX (SWIFT).
  - Developed custom C++ interfaces for stock exchange price feeds.
  - Built and configured 1,000+ daily EOD/BOD batch job sequences in BMC Control-M.
- **Outcome:** Successfully went live on schedule, followed by formal handover to regional steady-state production support teams.
