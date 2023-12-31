# Common Objects

## **Request**

#### **cohort**

Defines if cohort logic should be applied to the data.

<table><thead><tr><th width="150">Field</th><th width="150">Value</th><th width="438.2">Description</th></tr></thead><tbody><tr><td>enabled</td><td>bool</td><td><p>Enables or disables cohort grouping.</p><ul><li><code>true</code>: group events by cohort (install date)</li><li><code>false</code>: group events by day they occurred.</li></ul></td></tr><tr><td>dx</td><td>[int]</td><td><p>Controls which days after install (dx) to include in the calculation.</p><ul><li><strong>No value:</strong> Calculates events for all days.</li><li><strong>[0]:</strong> Calculates events on the day of install (d0).</li><li><strong>[0, 3]:</strong> Calculates events on d0 and d3.</li><li><strong>[0, 1, 2, 3]:</strong> Calculates events on d0, d1, d2, and d3.</li></ul></td></tr></tbody></table>

#### **interval** <a href="#pagination_request" id="pagination_request"></a>

Defines the date range which should be queried.

<table><thead><tr><th width="150">Field</th><th width="150">Value</th><th width="438.2"></th></tr></thead><tbody><tr><td>from</td><td>string</td><td>"YYYY-mm-dd" format. Data starting on this day will be included.</td></tr><tr><td>until</td><td>string</td><td>"YYYY-mm-dd" format. Data until this date (inclusive) will be included.</td></tr></tbody></table>

#### **pagination** <a href="#pagination_request" id="pagination_request"></a>

Specifies the request pagination frame.

<table><thead><tr><th width="150">Field</th><th width="150">Value</th><th width="438.2"></th></tr></thead><tbody><tr><td>page</td><td>int</td><td>The page which should be returned. Set <strong>0</strong> to get the very first page.</td></tr><tr><td>limit</td><td>int</td><td>Amount of rows to return in the response.</td></tr></tbody></table>

#### **orderBy**

Defines the sorting order for the results.

{% hint style="info" %}
You can order only by dimension or metrics which are specified in corresponding section.
{% endhint %}

<table><thead><tr><th width="150">Field</th><th width="150">Value</th><th width="434.2"></th></tr></thead><tbody><tr><td>name</td><td>string</td><td>Name of the metric or dimension to sort by.</td></tr><tr><td>order</td><td>string</td><td>Can be <strong>desc</strong> or <strong>asc</strong></td></tr></tbody></table>

#### **filters**

Allows to filter the data by dimensions.

The filter is written as an object where each key is a dimension and the value is a the selection of the requested dimension values. Values within one dimension have an **or** relation and dimensions within filters have an **and** relation.

For example, if one wants to get results only for the `app` dimension and your app store id is `my.awesome.app`, the filter will look like:

```
"filters": {
    "app": ["my.awesome.app"],
}
```

Available filters:

* app

#### **granularity**

Specifies how the time interval should be grouped. Available options:

* day
* week
* month

## Response

#### pagination <a href="#pagination_response" id="pagination_response"></a>

Specifies the response pagination frame.

<table><thead><tr><th width="150">Field</th><th width="150">Value</th><th width="444.2"></th></tr></thead><tbody><tr><td>total</td><td>int</td><td>Total amount of data rows available.</td></tr><tr><td>page</td><td>int</td><td>The number of the returned page.</td></tr><tr><td>limit</td><td>int</td><td>Number of rows on this page.</td></tr></tbody></table>

#### **row**

Row represents one row in the table. The keys will be the requested dimensions and metrics.

For example, if you filter the data for the `app` dimension with the value `my.awesome.app`, and request the metric `clicks`, your row will look like:

```
{
   "app": "my.awesome.app",
   "clicks": 830345
}
```

#### sum

Contains the summarized values of the requested metrics. Not only from the current page but from the whole time interval.

#### \<date>

Can be in different formats depending on the requested granularity.

| granularity in the request | key format in the response |
| -------------------------- | -------------------------- |
| day                        | YYYY-mm-dd                 |
| week                       | YYYY-ww                    |
| month                      | YYYY-mm                    |

#### `<metric>`

Is a requested metric.

For example, if one requests the metrics `clicks` and `averageRevenuePerInstall` with the granularity `day, the` response will look like:

```
{
   "2022-02-02": {
       "clicks": 100,
       "averageRevenuePerInstall": 3,5356
   }
}
```
