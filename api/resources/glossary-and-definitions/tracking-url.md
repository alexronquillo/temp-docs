# Tracking URL

A **tracking URL** specifies where to send data when users view or click your ads as well as what data you want to receive.

## Using Tracking URLs

Here is a typical workflow for using tracking URLs in justtrack:

<figure><img src="../../.gitbook/assets/Screenshot 2023-09-19 at 15.24.46.png" alt=""><figcaption><p>Tracking Flow</p></figcaption></figure>

1. When you connect a network to your company in justtrack, you usually need to configure two tracking URLs. The first is for when a user _sees_ your ad. (This is called an **impression**.) The second is for when a user _clicks_ your ad. At this stage, the tracking URLs are more like templates that specify what information you want to receive and the way you want to receive it; but [more on that later](tracking-url.md#parameters).
2. When you create a campaign in the network, you:
   1. Build a tracking URL that is specific to an app, platform, and goal\*.
   2. Add this tracking URL to the Network campaign.
3. When the network places the ad, it includes these tracker URLs.
4. When the user sees or clicks the ad, the network SDK sends tracking data to the correct URL where you can see the results in real time.

{% hint style="info" %}
\*Goals are not always required when building tracking URLs. They are only required if the network you're connecting supports both:

* Automatic campaign creation
* Sending spend data via tracking URLs
{% endhint %}

The data you receive from tracking URLs is valuable for things like understanding how effective your campaign is at achieving some goal or attributing user behaviours to the networks that run the campaigns.

{% hint style="warning" %}
Some networks don't support external tracking URLs. In those cases, we can't show impression or click data.
{% endhint %}

## Tracking URL components

A tracking URL is composed of three parts:

<figure><img src="../../.gitbook/assets/Screenshot 2023-09-19 at 15.24.58.png" alt=""><figcaption><p>Tracking URL Structure</p></figcaption></figure>

### Domain

The **domain** is the address that receives data about the network, the campaign, and user who sees or clicks your ad.

### Event

The **event** identifies the interaction the user had with your advertisement. The two possible values are:

* `view`
* `click`

### Parameters

The **parameters** specify the data you want to receive for your campaign. This data might include the user's country, the campaign type, or the goal you're basing your campaign on.

There are two types of parameters:

* Those that justtrack provides values for.
* Those that the network provides values for.

#### justtrack parameters

Some parameters are managed by justtrack. When you build a URL for a campaign, justtrack provides these values in the tracking URL:

| Parameter Name | Description                                                                  |
| -------------- | ---------------------------------------------------------------------------- |
| `goalName`     | Unique name of the default or custom goal                                    |
| `network`      | The justtrack id for the connected Network                                   |
| `storeId`      | Store ID for Apple iTunes/App Store app, or the package name for Google Play |

#### Network parameters

Some parameters are managed by the network. When a user interacts with the ad, the network provides values for these parameters:

<table><thead><tr><th>Parameter Name</th><th>Description</th><th data-type="checkbox">Included by default</th></tr></thead><tbody><tr><td><code>deviceId</code></td><td>Google Advertiser ID / Identifier for Advertisers</td><td>true</td></tr><tr><td><code>clickId</code></td><td>Network generated unique ID of the click (click links only)</td><td>true</td></tr><tr><td><code>viewId</code></td><td>Network generated unique ID of the view (view links only)</td><td>true</td></tr><tr><td><code>sourceId</code></td><td>Sub ID</td><td>true</td></tr><tr><td><code>sourceBundleId</code></td><td>Sub App ID</td><td>true</td></tr><tr><td><code>sourceCampaignId</code></td><td>Campaign ID of the network</td><td>true</td></tr><tr><td><code>creativeName</code></td><td>Name of the set of creative assets (provided by AppLike).</td><td>true</td></tr><tr><td><code>sourcePublisher</code></td><td>App publisher</td><td>true</td></tr><tr><td><code>creativeId</code></td><td>ID of the set of creative assets (provided by AppLike)</td><td>true</td></tr><tr><td><code>referrerId</code></td><td>Network generated unique ID of the referrer (click links only)</td><td>true</td></tr><tr><td><code>sourceUrl</code></td><td>Appstore URL in which the ad was shown</td><td>true</td></tr><tr><td><code>sourcePlacement</code></td><td>Placement within the publisher’s app</td><td>true</td></tr><tr><td><code>sourceCategory</code></td><td>Category of the publisher’s app in which the ad was shown</td><td>true</td></tr><tr><td><code>channel</code></td><td>Ad unit</td><td>true</td></tr><tr><td><code>adType</code></td><td>Type of shown creative asset</td><td>true</td></tr><tr><td><code>limitedAdTracking</code></td><td>"1" or "true" if ad tracking is limited, "0" or "false" if ad tracking is not limited</td><td>true</td></tr><tr><td><code>country</code></td><td>GEO country of the user (ISO3166 alpha-2)</td><td>true</td></tr><tr><td><code>osVersion</code></td><td>Operating system version</td><td>true</td></tr><tr><td><code>deviceType</code></td><td>Device type (tablet, phone, etc.)</td><td>true</td></tr><tr><td><code>deviceModel</code></td><td>Device model</td><td>true</td></tr><tr><td><code>deviceResolution</code></td><td>User device’s screen resolution</td><td>true</td></tr><tr><td><code>s2s</code></td><td>true/false: Describes if the click/view was executed by the server or by frontend</td><td>true</td></tr><tr><td><code>exchangeId</code></td><td>ID of ad exchange</td><td>true</td></tr><tr><td><code>exchangeName</code></td><td>Name of ad exchange</td><td>true</td></tr><tr><td><code>sourceName</code></td><td>Name of the publisher’s app in which the ad was shown</td><td>true</td></tr><tr><td><code>deviceVendor</code></td><td>Should be "apple" for ios platform or empty</td><td>true</td></tr><tr><td><code>adSetId</code></td><td>Ad set/group ID of the network</td><td>true</td></tr><tr><td><code>bidType</code></td><td>Campaign cost model ("CPI", "CPA", "CPC", "CPM", "CPV", "CPCV")</td><td>false</td></tr><tr><td><code>bidCurrency</code></td><td>CPI/CPA currency. This is required for spend tracking via clicks and views.</td><td>false</td></tr><tr><td><code>bidValue</code></td><td>CPI/CPA value (use . as decimal delimiter). This is required for spend tracking via clicks and views.</td><td>false</td></tr><tr><td><code>userAgent</code></td><td>User agent of the tracking event</td><td>false</td></tr><tr><td><code>ip</code></td><td>Current GEO IP of the tracking event</td><td>false</td></tr><tr><td><code>redirect</code></td><td>Prevents user getting redirected to the PlayStore if set to false</td><td>false</td></tr><tr><td><code>custom0</code></td><td>Optional custom parameter</td><td>false</td></tr><tr><td><code>custom1</code></td><td>Optional custom parameter</td><td>false</td></tr><tr><td><code>custom2</code></td><td>Optional custom parameter</td><td>false</td></tr><tr><td><code>custom3</code></td><td>Optional custom parameter</td><td>false</td></tr><tr><td><code>campaignType</code></td><td>"retargeting" for retargeting campaigns, "acquisition" for acquisition campaigns</td><td>false</td></tr><tr><td><code>optimizationType</code></td><td>The optimization type of the campaign</td><td>false</td></tr><tr><td><code>sourceCampaignName</code></td><td>Name of the campaign in network</td><td>false</td></tr><tr><td><code>adSetName</code></td><td>Name of the ad set, ad group, offer</td><td>false</td></tr></tbody></table>

#### Placeholders

When you connect a network to justtrack, you create templates for your tracking URLs. These templates use **placeholders** for the parameters so the values can be added later:

<figure><img src="../../.gitbook/assets/Screenshot 2023-09-19 at 15.25.08.png" alt=""><figcaption><p>Tracking URL with Placeholders</p></figcaption></figure>

By the time the user interacts with the ad, all these placeholders are replaced by real values.

{% hint style="warning" %}
You can include fixed values instead of placeholders if you don't want to receive dynamic tracking data from your network.
{% endhint %}

For justtrack parameters, the placeholders you provide are arbitrary. For network parameters, the placeholders you provide are specific to the network. Please consult the network's documentation to learn what placeholders you should use to get the correct data in your tracking URL.

## Learn more about Tracking URLs

* [Connect a Custom Network](../../../resources/glossary-and-definitions/broken-reference/)
* [View and Click Tracking](../../../resources/glossary-and-definitions/broken-reference/)
