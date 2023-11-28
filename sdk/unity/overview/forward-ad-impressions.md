# Forward Ad Impressions

Our SDK can forward ad impression data to the justtrack platform so you can track your app's ad revenue.&#x20;

We can automatically forward impressions for the following popular ad networks:

* IronSource
* Adjoe
* Unity
* Applovin
* Adcolony
* Chartboost

{% hint style="info" %}
For IronSource, refer to our [setup guide](../../android/integrate-third-party-sdks.md#ironsource) for combining our SDK with the IronSource SDK first.
{% endhint %}

However, if your ad network isn't in this list, you can manually forward impression data using `.ForwardAdImpression()`:

```csharp
JustTrackSDK.ForwardAdImpression(
    new AdImpression("format","sdk_name")
        .setNetwork("network")
        .setPlacement("placement")
        .setTestGroup("test_group")
        .setSegmentName("segment_name")
        .setInstanceName("instance_name")
        .setBundleId("bundle_id")
        .setRevenue(new Money(10.0,"USD")
);
```

This method accepts an `AdImpression` whose parameters are:

* **adFormat**: The format of the ad.
* **adSdkName**: The name of the SDK which provided the event, for example "ironsource" or "admob".

{% hint style="info" %}
The SDK name must be **lowercase**. So, for example, you would use "ironsource", not "Ironsource".
{% endhint %}

Additionally, you can use the following methods to set more dimensions:

| Method               | Argument                                            | Acceptable values                                                                                       |
| -------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| `.setNetwork()`      | The name of the ad network that provided the ad.    | String value or null.                                                                                   |
| `.setPlacement()`    | The placement of the ad.                            | String value or null.                                                                                   |
| `.setTestGroup()`    | The test group of the user, if you are A/B testing. | String value or null.                                                                                   |
| `.setSegmentName()`  | The name of the segment of the ad.                  | String value or null.                                                                                   |
| `.setInstanceName()` | The name of the instance of the ad.                 | String value or null.                                                                                   |
| `.setBundleId()`     | The app's bundleId.                                 | String value or null.                                                                                   |
| `.setRevenue()`      | The amount of revenue this ad generated.            | Money object with a non-negative amount. The currency must be a three-letter uppercase ISO 4217 string. |

&#x20;Upon success, `.forwardAdImpression()` returns true. If a parameter is invalid, false is returned.
