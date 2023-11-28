# Cost data sources

### Data Sources

Justtrack works with two cost data sources:

* Tracking link based (cost data metrics are collected from received conversion postbacks)
* Partner reporting APIs (cost data is imported from the networks directly)

We at justtrack recommend using tracking link cost data over imported cost data because it's available in realtime (as soon as the received click or view event is attributed to an install or goal) and on user level. Cost data is shown on the Acquisition overview as well as the campaign details page and is used in many calculated metrics.

However, not all networks support cost data on tracking links. That's why justtrack has many API integrations with partners. You are flexible to define which cost data you would like to see in the dashboard using the spend source configuration. The spend source can be set in each network per platform.

If spend source `spend importer` is selected, we use what we imported from the API. If spend source `global conversion event` is selected, we display the tracking link cost data.

{% hint style="info" %}
If spend source global conversion event is selected, we might still have an API importer available. We will then display the imported values in a separate metric.
{% endhint %}

{% hint style="danger" %}
Be careful when changing the spend source of a network, as it can affect the already collected cost metrics. Especially changing the spend source from `global conversion event` to the `spend import` is greatly discouraged.
{% endhint %}

### Available Data Sources and Dimensions

<table><thead><tr><th width="150">Partner</th><th width="150" data-type="checkbox">Tracking Link</th><th width="150" data-type="checkbox">Reporting API</th><th width="399">Available Dimensions</th></tr></thead><tbody><tr><td>AdColony</td><td>false</td><td>true</td><td><code>campaign</code>, <code>sourceId</code>, <code>adset</code></td></tr><tr><td>Adjoe</td><td>true</td><td>true</td><td><code>campaign</code>, <code>sourceId</code>, <code>adset</code></td></tr><tr><td>Applovin</td><td>false</td><td>true</td><td><code>campaign</code>, <code>sourceId</code></td></tr><tr><td>Facebook</td><td>false</td><td>true</td><td><code>campaign</code>, <code>adset</code></td></tr><tr><td>Fluent</td><td>true</td><td>true</td><td><code>campaign</code></td></tr><tr><td>Fyber</td><td>false</td><td>true</td><td><code>campaign</code></td></tr><tr><td>Google Ads</td><td>false</td><td>true</td><td><code>campaign</code>, <code>adset</code></td></tr><tr><td>Ironsource</td><td>false</td><td>true</td><td><code>campaign</code>, <code>sourceId</code></td></tr><tr><td>Kayzen</td><td>false</td><td>true</td><td><code>campaign</code>, <code>sourceId</code></td></tr><tr><td>Mintegral</td><td>true</td><td>true</td><td><code>campaign</code>, <code>sourceId</code></td></tr><tr><td>Mobvista</td><td>false</td><td>true</td><td><code>campaign</code></td></tr><tr><td>Motive</td><td>true</td><td>true</td><td><code>campaign</code></td></tr><tr><td>Offertoro</td><td>true</td><td>true</td><td><code>campaign</code></td></tr><tr><td>Tapjoy</td><td>true</td><td>true</td><td><code>campaign</code>, <code>sourceId</code>, <code>adset</code></td></tr><tr><td>TikTok</td><td>false</td><td>true</td><td><code>campaign</code>, <code>adset</code></td></tr><tr><td>Unity</td><td>true</td><td>true</td><td><code>campaign</code>, <code>sourceId</code></td></tr><tr><td>Vungle</td><td>true</td><td>true</td><td><code>campaign</code>, <code>sourceId</code></td></tr></tbody></table>

### Configuration

In order to use the cost metric integration through the `spend import` data source, make sure to fill in your credentials for the networks you want to import cost metrics for. The credentials can be edited via the `Credentials` Tab on the networks Admin page.

{% hint style="info" %}
If import source is `spend import`, the multicountry capability cannot be edited.
{% endhint %}
