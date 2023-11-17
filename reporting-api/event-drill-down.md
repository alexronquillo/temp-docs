# Event Drill Down

## About

The Drill Down API provides access to the same data which is available on the Engagement: Event Drill Down page of the justtrack dashboard.

<details>

<summary><strong>Supp</strong>orted metrics</summary>

```
[
  "totalEventsCount"
]
```

</details>

<details>

<summary>Supported dimensions</summary>

```
[
  "app",
  "eventName",
  "country",
  "installAppVersionName",
  "network.id"
]
```

</details>

## Table API

Use the Table API for feeding your own drill down tables. Send a POST request to:

> `curl -H X-API-Key: <API_KEY> https://api.justtrack.io/reporting/v1/drill-down/table`

### Request

```
{
   "cohort": {
       "enabled": bool,
       "dx": [int]
   },
   "interval": {
       "from": "YYYY-mm-dd",
       "until": "YYYY-mm-dd"
   },
   "metrics": [string],
   "dimensions": [string],
   "filters": {
       "<dimension>": [string],
   },
   "pagination": {
       "page": int,
       "limit": int
   },
   "orderBy": {
       "name": string,
       "direction": string,
   }
}

```

<table><thead><tr><th width="170.54133348659428">Name</th><th width="150">Type</th><th width="222.13953488372093">Description</th></tr></thead><tbody><tr><td>cohort</td><td><a href="common-objects.md#cohort">Cohort</a> object</td><td>Cohort or daily view.</td></tr><tr><td>interval</td><td><a href="common-objects.md#pagination_request">Interval</a> object</td><td>An interval within which data should be aggregated.</td></tr><tr><td>metrics</td><td>[]string</td><td>A list of requested metrics.</td></tr><tr><td>dimensions</td><td>[]dimensions</td><td>A list of dimensions by which data should be split. You can request up to 3 dimensions.</td></tr><tr><td>filters</td><td><a href="common-objects.md#filters">Filters</a> object</td><td>Filters to limit requested data. Optional.</td></tr><tr><td>pagination</td><td><a href="common-objects.md#pagination_request-1">Pagination</a> object</td><td>Batch number and amount of data rows to return.</td></tr><tr><td>orderBy</td><td><a href="common-objects.md#orderby">OrderBy</a> object</td><td>Descending or ascending order by selected metric or dimension.</td></tr></tbody></table>

### **Response**

```
{
   "pagination": {
       "page": int,
       "limit": int,
       "total": int
   },
   "rows": [
       {
           "<dimension>": string,
           "<metric>": float
       }
   ],
   "sum": {
       "<metric>": float
   }
}

```

<table><thead><tr><th width="150">Name</th><th width="187.97838673358947">Type</th><th>Description</th></tr></thead><tbody><tr><td>pagination</td><td><a href="common-objects.md#pagination_response">Pagination</a> object</td><td>Used pagination settings and total amount of data rows.</td></tr><tr><td>rows</td><td>[]<a href="common-objects.md#row">Row</a></td><td>A list of data rows.</td></tr><tr><td>sum</td><td><a href="common-objects.md#sum">Sum</a> object</td><td>Sum for all table entries (not only for the requested page).</td></tr></tbody></table>

## Graph APi

The Graph API offers the same data as Table API with more flexible date grouping options.

> curl -H X-API-Key: \<API\_KEY> https://api.justtrack.io/reporting/v1/drill-down/graph

### Request

```
{
   "cohort": {
       "enabled": bool,
       "dx": [int]
   },
   "interval": {
       "from": "YYYY-mm-dd",
       "until": "YYYY-mm-dd"
   },
   "granularity": string,
   "metrics": [string],
   "filters": {
       "<dimension>": [string]
   }
}

```

<table><thead><tr><th width="150">Name</th><th width="150">Type</th><th width="222.13953488372093">Description</th></tr></thead><tbody><tr><td>cohort</td><td><a href="common-objects.md#cohort">Cohort</a> object</td><td>Cohort or daily view.</td></tr><tr><td>interval</td><td><a href="common-objects.md#pagination_request">Interval</a> object</td><td>An interval within which data should be aggregated.</td></tr><tr><td>granularity</td><td><a href="common-objects.md#granularity">Granularity</a> object</td><td>Scale of the data aggregation.</td></tr><tr><td>metrics</td><td>[]string</td><td>A list of requested metrics.</td></tr><tr><td>filters</td><td><a href="common-objects.md#filters">Filters</a> object</td><td>Filters to limit requested data. Optional.</td></tr></tbody></table>

### Response

```
{
   "<date>": {
       "<metric>": float
   }
}
```

[\<date>](common-objects.md#less-than-date-greater-than) stands for the date within which data was aggregated. Depends on the requested granularity.

[\<metric>](common-objects.md#less-than-metric-greater-than) stands for the requested metric name and contains float value.
