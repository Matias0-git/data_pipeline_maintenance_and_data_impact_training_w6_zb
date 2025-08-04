# Week 6: Zach bootcamp - Data Pipeline Maintenance
With this fifth publication I want to showcase what we did on week 6 of the zach bootcamp. I am going to cover the concepts that he taught us and the hands-on labs.

First of all, for the concepts that were introduced in week 6 are:

Day 1
- How to do a good data migration?
- How to setup runbooks on-call rotation?
- Ownership models of datasets
  - Who owns what ->
    - Data sets
    - Data pipeline
    - Data documentation
    - Metrics
    - Experiments
  - Centralized vs Embedded teams
- Common Ownership and maintenance problems
  - There are problems when:
    - Data engineers own logging
    - Data scientist write pipelines
    - Data engineers own metrics
- Team models for data engineering
- The difficult parts of data engineering
  - High expectations which may lead to burnout if you build pipelines as if you are trying to sprint a marathon
  - Data quality issues
  - Unclear priorities / Adhoc requests
- How to set proper SLAs
Lab 1
- No lab this week it was an overview to relax from the prior intense week
Day 2
- Signals of tech debt in data engineering
- How to fix time consuming pipelines
- Proper upgrades for pipelines
- When to use sample?
- When to use bucketing?
- Where do the large cloud bills come from and how to minimize them
  - Usage of subpartitions
- How to deal with multiples sources of truth
- Building a pipeline spec
- Different models for getting ahead of tech debt
  - Fix as you go
  - Allocating dedicated time each quarter
  - Have the on-call person do tech debt
- Data migration models
- The importance of knowing your users (upstream and downstream owners)

# Book suggestion to complete the assignments of week 6
For this particular case I am going to suggest the following book:
- Data engineering best practices: architect robust and cost-effective data solutions in the cloud era from Richard J. Schiller

# Assignments of week 6: [Assignment on zach's github](https://github.com/DataExpert-io/data-engineer-handbook/blob/main/bootcamp/materials/6-data-pipeline-maintenance/homework/homework.md)

I built a document which is taylor to manage 5 data pipelines, outlining their ownership, an on-call schedule including holidays, and potential failure points for investor-facing runbooks.








