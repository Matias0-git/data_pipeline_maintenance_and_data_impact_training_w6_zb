# Week 6 Data Pipeline Maintenance Plan

### Objective:
To establish clear ownership, an equitable on-call schedule, and initial run book considerations for five critical data pipelines covering Profit, Growth, and Engagement, specifically focusing on investor-reported metrics.

---

## 1. Pipeline Ownership

To ensure robust support and clear accountability, each pipeline has a primary and secondary owner. This allows for redundancy and knowledge sharing.

* **Profit - Unit-level profit needed for experiments:**
    * Primary Owner: Data Engineer A
    * Secondary Owner: Data Engineer B
* **Profit - Aggregate profit reported to investors:**
    * Primary Owner: Data Engineer B
    * Secondary Owner: Data Engineer C
* **Growth - Aggregate growth reported to investors:**
    * Primary Owner: Data Engineer C
    * Secondary Owner: Data Engineer D
* **Growth - Daily growth needed for experiments:**
    * Primary Owner: Data Engineer D
    * Secondary Owner: Data Engineer A
* **Engagement - Aggregate engagement reported to investors:**
    * Primary Owner: Data Engineer A
    * Secondary Owner: Data Engineer C

---

## 2. On-Call Schedule

Our on-call schedule operates on a weekly rotation, ensuring equitable distribution of responsibility and sufficient time off. We've incorporated considerations for public holidays to minimize disruption.

* **Week 1:** Data Engineer A (Primary On-Call), Data Engineer B (Secondary On-Call)
* **Week 2:** Data Engineer B (Primary On-Call), Data Engineer C (Secondary On-Call)
* **Week 3:** Data Engineer C (Primary On-Call), Data Engineer D (Secondary On-Call)
* **Week 4:** Data Engineer D (Primary On-Call), Data Engineer A (Secondary On-Call)
* *(The rotation repeats every 4 weeks)*

**Holiday Policy:**

* If a public holiday falls within a primary on-call engineer's week, the secondary on-call engineer will cover the holiday period.
* If both primary and secondary engineers are unavailable due to holiday conflicts, the team will re-distribute the on-call duties for that specific week, ensuring continuous coverage. This will be communicated and agreed upon at least two weeks in advance.
* An on-call handover meeting will take place every Friday to discuss any ongoing issues, potential alerts, and to ensure a smooth transition.

---

## 3. Run Books for Investor-Reported Pipelines

Run books provide essential documentation for troubleshooting and maintaining critical pipelines. Below are outlines for the run books for pipelines reporting metrics to investors, focusing on potential failure points.

### 3.1. Run Book: Aggregate Profit Reported to Investors

**Purpose:** This pipeline calculates and delivers the aggregate profit metrics essential for investor reports.

**Potential Things That Could Go Wrong:**

* **Data Source Issues:** Upstream data source is down, inaccessible, corrupted, malformed, or delayed.
* **Data Transformation Failures:** Incorrect aggregation logic, loss of precision, incorrect joins, or resource exhaustion during processing.
* **Data Loading/Storage Issues:** Target data warehouse/database is offline/inaccessible, insufficient disk space, schema drift, or network connectivity issues.
* **Scheduling/Orchestration Failures:** Scheduled job fails to trigger, dependencies not met, or orchestration tool internal errors.
* **Data Quality/Validation Failures:** Outputted profit figures deviate from expected ranges, data freshness checks fail, or discrepancies with other reports.
* **Security/Permissions Issues:** Expired/incorrect credentials or revoked access permissions for service accounts.

### 3.2. Run Book: Aggregate Growth Reported to Investors

**Purpose:** This pipeline computes and delivers aggregate growth metrics vital for investor communications.

**Potential Things That Could Go Wrong:**

* **Data Source Issues:** Key growth drivers unavailable/incomplete, inconsistent data reporting, or delayed feeds for historical comparisons.
* **Data Transformation Failures:** Incorrect time windowing, errors in baseline data, mathematical errors in growth calculation, or issues handling missing time series data.
* **Data Loading/Storage Issues:** Target data mart/dashboarding tool's data store unreachable, data integrity constraint violations, or performance degradation in target database.
* **Scheduling/Orchestration Failures:** Pipeline run exceeding allocated time, dependent pipelines failing, or configuration errors in orchestration system.
* **Data Quality/Validation Failures:** Reported growth figures show unexpected trends, discrepancies with manual spot checks, or alerts from data validation rules.
* **External API/Service Dependencies:** Failure to retrieve data from third-party APIs or API rate limits exceeded.

### 3.3. Run Book: Aggregate Engagement Reported to Investors

**Purpose:** This pipeline collects and aggregates engagement metrics for investor reporting, providing insights into user activity and platform health.

**Potential Things That Could Go Wrong:**

* **Data Source Issues:** Event tracking systems are down/experiencing data loss, schema changes in raw event data, missing/maldformed user/session IDs, or backlogs in event queues.
* **Data Transformation Failures:** Incorrect aggregation of user actions, failure to filter bot traffic, incorrect attribution, or performance bottlenecks during stream processing.
* **Data Loading/Storage Issues:** Destination for aggregated metrics unavailable, data type mismatches, or indexing issues on target database.
* **Scheduling/Orchestration Failures:** Pipeline jobs skipped/fail to restart, unfulfilled dependencies on user profile data, or resource contention.
* **Data Quality/Validation Failures:** Reported engagement metrics show uncharacteristic trends, discrepancies with raw event counts, or alerts from anomaly detection systems.
* **Compliance/Privacy Issues:** Accidental inclusion of PII or failure to correctly anonymize/pseudonymize sensitive data.

---
