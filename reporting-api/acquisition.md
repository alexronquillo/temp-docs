# Acquisition

## About

The Acquisition API lets you request the most relevant metrics for your apps which are available on the Acquisition Overview page of the justtrack dashboard.

#### Supported Metrics

<table><thead><tr><th width="341.23779193205945">Metric</th><th width="150">Short</th><th>About</th></tr></thead><tbody><tr><td>activeUsers</td><td></td><td>Number of users with opens (unique opens)</td></tr><tr><td>advertisingSpend</td><td></td><td>Sum of advertising spend from source defined per network</td></tr><tr><td>averageRevenueEventValue</td><td>AREV</td><td>AREV - Average revenue per revenue event</td></tr><tr><td>averageRevenuePerActiveUser</td><td>ARPAU</td><td>ARPAU - Average revenue per active user</td></tr><tr><td>averageSessionLength</td><td></td><td>Sum of time spend in app divided by number of sessions</td></tr><tr><td>averageTimeSpendInApp</td><td></td><td>Sum of time spend in app divided by number of active users</td></tr><tr><td>blockedUsers</td><td></td><td>Number of blocked users</td></tr><tr><td>clicks</td><td></td><td>Number of ad clicks</td></tr><tr><td>clickThroughRate</td><td>CTR</td><td>CTR - Number of ad clicks divided by number of ad impressions</td></tr><tr><td>clickToInstallRate</td><td>CTI</td><td>CTI - Number of installs divided by number of ad clicks</td></tr><tr><td>contributionMargin1</td><td>CM1</td><td>CM1 - Sum of revenue minus sum of advertising spend</td></tr><tr><td>contributionMargin1Rate</td><td>CM1%</td><td>CM1% - Sum of contribution margin divided by sum of revenue</td></tr><tr><td>contributionMargin2</td><td>CM2</td><td>CM2 - Sum of revenue minus sum of spendum of spend</td></tr><tr><td>contributionMargin2Rate</td><td>CM2%</td><td>CM2% - Sum of contribution margin 2 divided by sum of revenue</td></tr><tr><td>costPerAction</td><td>CPA</td><td>CPA - Sum of advertising spend divided by number of successfully sent action postbacks</td></tr><tr><td>costPerInstall</td><td>CPI</td><td>CPI - Sum of advertising spend divided by number of installs</td></tr><tr><td>effectiveCostPerClick</td><td>eCPC</td><td>eCPC - Effective cost per ad click</td></tr><tr><td>effectiveCostPerView</td><td>eCPV</td><td>eCPV - Effective cost per ad impression</td></tr><tr><td>effectiveCostPerMille</td><td>eCPM</td><td>eCPM - Effective cost per thousand ad impressions</td></tr><tr><td>externalAdvertisingSpend</td><td></td><td>Sum of advertising spend imported from network(s)</td></tr><tr><td>externalClicks</td><td></td><td>Number of ad clicks imported from network(s)</td></tr><tr><td>externalImpressions</td><td></td><td>Number of ad impressions imported from network(s)</td></tr><tr><td>impressions</td><td></td><td>Number of ad impressions</td></tr><tr><td>installs</td><td></td><td>Number of installs</td></tr><tr><td>installRate</td><td>IR</td><td>IR - Number of installs divided by number of ad impressions</td></tr><tr><td>installsPerMille</td><td>IPM</td><td>IPM - Number of installs per thousand ad impressions</td></tr><tr><td>monetizationAdImpressions</td><td></td><td>Number of successful ad impressions</td></tr><tr><td>monetizationAdImpressionsBanner</td><td></td><td>Number of successful ad impressions with banner type</td></tr><tr><td>monetizationAdImpressionsInterstitial</td><td></td><td>Number of successful ad impressions with interstitial type</td></tr><tr><td>monetizationAdImpressionsRewarded</td><td></td><td>Number of successful ad impressions with rewarded type</td></tr><tr><td>monetizedUsers</td><td>MU</td><td>MU - Number of users with revenue event in the selected time range</td></tr><tr><td>payout</td><td></td><td>Sum of concluded payouts (the defining timestamp is the conclude date)</td></tr><tr><td>payoutPerActiveUser</td><td>PPAU</td><td>PPAU - Sum of payout divided by number of active users</td></tr><tr><td>payoutRate</td><td></td><td>Sum of payout divided by sum of revenue</td></tr><tr><td>restrictedUsers</td><td></td><td>Number of restricted users</td></tr><tr><td>retentionRate</td><td></td><td>Number of active users divided by number of installs</td></tr><tr><td>returnOnAdvertisingSpend</td><td>ROAS</td><td>ROAS - Sum of revenue divided by sum of Advertising Spend</td></tr><tr><td>returnOnInvestment</td><td>ROI</td><td>ROI - Sum of revenue divided by sum of Spend</td></tr><tr><td>revenue</td><td></td><td>Sum of revenue</td></tr><tr><td>revenueEvents</td><td></td><td>Number of revenue events</td></tr><tr><td>skadInstalls</td><td></td><td>Number of SKAd Postbacks sent by the network</td></tr><tr><td>spend</td><td></td><td>Sum of advertising spend and payouts</td></tr><tr><td>suspiciousUsers</td><td></td><td>Number of suspicious users</td></tr></tbody></table>

<details>

<summary>Supported dimensions</summary>

```
[
  "app",
  "country",
  "date",
  "network.id",
  "campaign.id",
  "adsetName",
  "platform.id",
  "channel.id",
  "country.id",
  "dayOfWeek",
  "week",
  "month",
  "user.type",
  "campaign.type",
  "sourcePublisher",
  "sourceId",
  "sourceName", 
  "exchangeId",
  "exchangeName", 
  "sourceBundleId",
  "sourceCategory",
  "sourcePlacement", 
  "sourceUrl", 
  "externalAdSetId",
  "adType",
  "creativeName",
  "installAppVersionName",
  "creative.id", 
  "initialClientVersion",
  "installNumber",
  "testGroupId"
]
```

</details>

## Table API

This API provides data to build custom tables. The metrics are grouped by the requested dimensions.

> `curl -H X-API-Key: <API_KEY> https://api.justtrack.io/reporting/v1/acquisition/table`

### Request

The general request to the Table API looks like:

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

<table><thead><tr><th width="170.54133348659428">Name</th><th width="150">Type</th><th width="222.13953488372093">Description</th></tr></thead><tbody><tr><td>cohort</td><td><a href="common-objects.md#cohort">Cohort</a> object</td><td>Cohort or daily logic</td></tr><tr><td>interval</td><td><a href="common-objects.md#pagination_request">Interval</a> object</td><td>Time interval within which data should be aggregated</td></tr><tr><td>metrics</td><td>[]string</td><td>List of requested metrics</td></tr><tr><td>dimensions</td><td>[]dimensions</td><td><p>List of dimensions by which data should be split</p><p>You can request up to 3 dimensions</p></td></tr><tr><td>filters</td><td><a href="common-objects.md#filters">Filters</a> object</td><td>Filters to limit requested data. Optional</td></tr><tr><td>pagination</td><td><a href="common-objects.md#pagination_request-1">Pagination</a> object</td><td>Batch number and amount of data rows to return</td></tr><tr><td>orderBy</td><td><a href="common-objects.md#orderby">OrderBy</a> object</td><td>Descending or ascending order by selected metric or dimension</td></tr></tbody></table>

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

<table><thead><tr><th width="150">Name</th><th width="187.97838673358947">Type</th><th>Description</th></tr></thead><tbody><tr><td>pagination</td><td><a href="common-objects.md#pagination_response">Pagination</a> object</td><td>Used pagination settings and total amount of data rows</td></tr><tr><td>rows</td><td>[]<a href="common-objects.md#row">Row</a></td><td>List of data rows</td></tr><tr><td>sum</td><td><a href="common-objects.md#sum">Sum</a> object</td><td>Sum for all table entries (not only for the requested page)</td></tr></tbody></table>

## Graph APi

The Graph API offers the same data as Table API with more flexible date grouping options.

> curl -H X-API-Key: \<API\_KEY> https://api.justtrack.io/reporting/v1/acquisition/graph

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

<table><thead><tr><th width="150">Name</th><th width="150">Type</th><th width="222.13953488372093">Description</th></tr></thead><tbody><tr><td>cohort</td><td><a href="common-objects.md#cohort">Cohort</a> object</td><td>Cohort or daily logic</td></tr><tr><td>interval</td><td><a href="common-objects.md#pagination_request">Interval</a> object</td><td>Time interval within which data should be aggregated.</td></tr><tr><td>granularity</td><td><a href="common-objects.md#granularity">Granularity</a> object</td><td>Scale of the data aggregation</td></tr><tr><td>metrics</td><td>[]string</td><td>List of requested metrics</td></tr><tr><td>filters</td><td><a href="common-objects.md#filters">Filters</a> object</td><td>Optional filters to limit the requested data</td></tr></tbody></table>

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
