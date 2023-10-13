+++
author = "Oleh P"
title = "Data Export From New Relic"
date = "2023-10-13"
description = "Discover the key to harnessing New Relic data through effective exporting methods"
tags = [
    "newrelic"
]
categories = [
    "Monitoring"
]
draft = false
image = "img/cover.jpg"
+++


New Relic support two approaches for data exporting:

- Streaming data export
- Historical data export

**Streaming Export**

Stream data out of New Relic (as it is being ingested)

A streaming data export sends out data exclusively at [ingestion](https://forum.newrelic.com/s/hubtopic/aAX8W0000008dl6WAA/void(0)) by New Relic, so any data from the past 12 hours since ingestion

Supports sending data to AWS Kinesis Firehose or Azure Event Hub

**Limits**

- The amount of data you can stream per month is limited by your total [ingested data](https://docs.newrelic.com/docs/accounts/accounts-billing/new-relic-one-pricing-billing/data-ingest-billing/#usage-calculation) per month.

**Requirements**

**Permissions**:

- Data Plus subscription
- core user or full platform user
- Capability: the [streaming data capability](https://docs.newrelic.com/docs/accounts/accounts-billing/new-relic-one-user-management/user-capabilities/#data-platform)

**Configured** Azure Event Hub or AWS Kinesis Firehose to receive New Relic data.

**NRQL**:

- No aggregation
- Query cannot have a FACET clause, COMPARE WITH, or LOOKUP
- Nested queries are not supported.
- Metrics are not supported.

Time Range:

- Past 12 hrs

**How to create a streaming export rule**

```sql
mutation {
  streamingExportCreateRule(
    accountId: YOUR_NR_ACCOUNT_ID
    ruleParameters: {
      description: "ADD_RULE_DESCRIPTION"
      name: "PROVIDE_RULE_NAME"
      nrql: "SELECT * FROM NodeStatus"
    }
    azureParameters: {
      eventHubConnectionString: "YOUR_EVENT_HUB_SAS_CONNECTION_STRING"
      eventHubName: "YOUR_EVENT_HUB_NAME"
    }
  ) {
    id
    status
  }
}
```

**Historical data export**

historical data export feature can be used to run a NRQL query that returns 200,000,000 data points in a response (instead of the usual [limit of 2000](https://docs.newrelic.com/docs/query-your-data/nrql-new-relic-query-language/get-started/nrql-syntax-clauses-functions/#sel-limit)) and has no query timeout. The results are returned as one or more JSON files.

The results files contain approximately 100MB or less of GZIP compressed JSON

**Requirements**

- Data Plus
- core user or full platform user

**Limits**

**Usage:**

- Return < 200M events
- Inspect < 5 B events
- Max 2 concurrent exports per account

**Data:**

- Matric timeslice data - not available
- Dimensional metrics - not availble
- Infra events (*Sample) - not available

**Time Range:**

- must end at least 12 hours in the past

**How to Create Historical Export**

```sql
mutation {
  historicalDataExportCreateExport(
    accountId: YOUR_ACCOUNT_ID
    nrql: "FROM Transaction SELECT duration, appId WHERE appName = 'interesting-application' SINCE '2023-09-11 11:05:00-0600' UNTIL '2022-09-11 11:10:00-0600'"
  ) {
    percentComplete
    nrql
    status
    id
    message
  }
}
```

**Links**

- Introducing Streaming Data Export: Export your data for compliance and analysis -[https://forum.newrelic.com/s/hubtopic/aAX8W0000008dl6WAA/introducing-streaming-data-export-export-your-data-for-compliance-and-analysis](https://forum.newrelic.com/s/hubtopic/aAX8W0000008dl6WAA/introducing-streaming-data-export-export-your-data-for-compliance-and-analysis)
- Streaming data export: Send your data to an AWS Kinesis Firehose or Azure Event Hub - [https://docs.newrelic.com/docs/apis/nerdgraph/examples/nerdgraph-streaming-export/](https://docs.newrelic.com/docs/apis/nerdgraph/examples/nerdgraph-streaming-export/)
- Historical data export: return larger NRQL responses - [https://docs.newrelic.com/docs/apis/nerdgraph/examples/nerdgraph-historical-data-export/](https://docs.newrelic.com/docs/apis/nerdgraph/examples/nerdgraph-historical-data-export/)
- Export your New Relic data for compliance and deeper data exploration - [https://newrelic.com/blog/nerdlog/historical-and-streaming-data-exports](https://newrelic.com/blog/nerdlog/historical-and-streaming-data-exports)