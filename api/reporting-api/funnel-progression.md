# Funnel Progression

## About

The Funnel Progression API provides access to the same data that is available on the [_Game Progression Funnel_](https://dashboard.justtrack.io/app-analytics/game-progression) page in the justtrack platform.

<details>

<summary><strong>Supp</strong>orted metrics</summary>

```
[
  "churnRate",
  "usersOfStepOne"
]
```

</details>

## Table & Graph API

Send a POST request to:

> `curl -H X-API-Key: <API_KEY> https://api.justtrack.io/reporting/v1/funnel/progression`

### Request

```
{
    "interval": {
        "from": "2023-08-01",
        "until": "2023-08-02" 
    },
    "metrics": [ 
        "churnRate", 
        "usersOfStepOne"
    ],
    "dimension": "eventDimension[DIMENSION NAME]",
    "filters": { 
        "app": [
            "APP NAME" 
        ]
    }, 
    "pagination": {
        "page": 0,
        "limit": 25 
    }
}
```

<table><thead><tr><th width="170.54133348659428">Name</th><th width="150">Type</th><th width="222.13953488372093">Description</th></tr></thead><tbody><tr><td>dimension</td><td>string</td><td><p>A dimension by which game events will be selected. Here, you have two options depends on your SDK setup:</p><ul><li>eventDimension[element_id]</li><li>eventDimension[jt_level_name]</li></ul></td></tr><tr><td>metrics</td><td>[]string</td><td>A list of requested metrics.</td></tr><tr><td>interval</td><td><a href="common-objects.md#pagination_request">Interval</a> object</td><td>An interval within which data should be aggregated.</td></tr><tr><td>filters</td><td><a href="common-objects.md#filters">Filters</a> object</td><td>Filters to limit requested data. The <code>app</code> filter is required for this api.</td></tr><tr><td>pagination</td><td><a href="common-objects.md#pagination_request-1">Pagination</a> object</td><td>Batch number and amount of data rows to return.</td></tr></tbody></table>

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
           "event": string,
           "step": string,
           "<dimension>": string,
           "<metric>": float
       }
   ]
}

```

<table><thead><tr><th width="150">Name</th><th width="187.97838673358947">Type</th><th>Description</th></tr></thead><tbody><tr><td>pagination</td><td><a href="common-objects.md#pagination_response">Pagination</a> object</td><td>Used pagination settings and total amount of data rows.</td></tr><tr><td>rows</td><td>[]<a href="common-objects.md#row">Row</a></td><td>A list of data rows. Also rows objects always contain <strong>event</strong> and <strong>step</strong> fields with corresponding values.</td></tr></tbody></table>
