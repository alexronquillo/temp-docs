# Cohort

## About

The Cohort API provides data which is available on the Cohort Analysis view on the justtrack dashboard.

#### Supported Metrics

| Metric                                | About                                                      |
| ------------------------------------- | ---------------------------------------------------------- |
| retentionRate                         | Number of active users divided by number of installs       |
| monetizationAdImpressions             | Number of successful ad impressions                        |
| monetizationAdImpressionsBanner       | Number of successful ad impressions with banner type       |
| monetizationAdImpressionsInterstitial | Number of successful ad impressions with interstitial type |
| monetizationAdImpressionsRewarded     | Number of successful ad impressions with rewarded type     |

## Table & Graph API

For cohort purposes you need only one request to feed your tables and graphs.

> `curl -H X-API-Key: <API_KEY> https://api.justtrack.io/reporting/v1/cohort`

### Request

General request to the Cohort API should look like:

```
{
   "cumulative": bool,
   "interval": {
       "from": "YYYY-mm-dd",
       "until": "YYYY-mm-dd"
   },
   "filters": {
       "<dimension>": [string]
   },
   "dx": [],
   "metric": string
}
```

<table><thead><tr><th width="166.88508818813472">Name</th><th width="150">Type</th><th width="222.13953488372093">Description</th></tr></thead><tbody><tr><td>cumulative</td><td>bool</td><td><p>Set <strong>false</strong> for non-cumulative aggregation for each day.</p><p>Set <strong>true</strong> for cumulative aggregation (each day number will contain the result of the previous one).</p></td></tr><tr><td>interval</td><td><a href="common-objects.md#pagination_request">Interval</a> object</td><td>The date range within the app installation happened.</td></tr><tr><td>filters</td><td><a href="common-objects.md#filters">Filters</a> object</td><td>Filters to limit requested data. Optional.</td></tr><tr><td>dx</td><td>[]int</td><td>For every selected dx the response will include one data point of the requested metric. For example, if you want to get metrics for the first 3 days (including install date), your <code>dx</code> value has to be <code>[0, 1, 2]</code>. You can request up to 90.</td></tr><tr><td>metric</td><td>string</td><td>Metric to calculate.</td></tr></tbody></table>

### Response

```
{
    "unit": string,
    "average": {
        "cohortSize": float,
        "values": [float]
    },
    "rows": {
        "<YYYY-mm-dd>": {
            "cohortSize": float,
            "values": [float]
        }
    }
}
```

#### unit

The unit for the values. Can be **$** or **%,** depending on the metric.

#### average

A Row with an average value for all days.

#### rows

List of objects, where each entry represents data for the specific table row. The Key is the date on which the installation of the app has happened.

| Field      | Value    |                                                                                           |
| ---------- | -------- | ----------------------------------------------------------------------------------------- |
| cohortSize | float    | Amount of installs at the specific day.                                                   |
| values     | \[float] | List of floats, where each value corresponds to the requested day after the installation. |
