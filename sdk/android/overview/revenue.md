# Revenue

The justtrack SDK can track advertisement and in-app purchase revenue for you. In-app purchase revenue is always tracked automatically, advertising revenue can be tracked automatically from the IronSource SDK right now (see [Third-Party Integrations](broken-reference)). If you are using another SDK to deliver ads for your users, you can track the impressions manually.

## Forward in-app purchases

If the user performs an in-app product or subscription purchase, you can forward the purchase via the justtrack SDK to our backend. By default, this is already enabled and every purchase of the user will be forwarded automatically. You can enable or disable the integration by calling `setAutomaticInAppPurchaseTracking` when creating the SDK instance or on the SDK:

{% tabs %}
{% tab title="Java" %}
```java
SdkBuilder builder = /* create the builder somehow */ new JustTrackSdkBuilder(this, BuildConfig.APP_KEY);
JustTrackSdk sdk = builder
        // configure the SDK when creating an instance:
        .setAutomaticInAppPurchaseTracking(forwardPurchasesAutomatically)
        // other options...
        .build();
// configure an already existing SDK instance:
sdk.setAutomaticInAppPurchaseTracking(forwardPurchasesAutomatically);
```
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
val builder: SdkBuilder = /* create the builder somehow */ JustTrackSdkBuilder(this, BuildConfig.APP_KEY)
val sdk: JustTrackSdk = builder
    // configure the SDK when creating an instance:
    .setAutomaticInAppPurchaseTracking(forwardPurchasesAutomatically)
    // other options...
    .build()
// configure an already existing SDK instance:
sdk.setAutomaticInAppPurchaseTracking(forwardPurchasesAutomatically)
```
{% endtab %}
{% endtabs %}

When enabled, all purchases will be reported automatically to the justtrack backend and, if you have correctly configured purchase validation, show up as revenue for your app.

You have to [configure a service account](https://docs.justtrack.io/product-features/cost-and-revenue-aggregation/in-app-purchase-revenue/google-play-store) to correctly validate purchases.

## Forward Ad Impressions

Our SDK can forward ad impression data to the justtrack platform so you can track your app's ad revenue.&#x20;

We can automatically forward ad impressions for the following partners:

* IronSource
* Adjoe
* Unity
* Applovin
* Adcolony
* Chartboost

{% hint style="info" %}
For IronSource, refer to our [setup guide](../integrate-third-party-sdks.md#ironsource) for combining our SDK with the IronSource SDK first.
{% endhint %}

However, if your ad network isn't in this list, you can manually forward impression data using `.forwardAdImpression()`:

{% tabs %}
{% tab title="Java" %}
```java
JustTrackSdk sdk = JustTrack.getInstance();
sdk.forwardAdImpression(
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
{% endtab %}

{% tab title="Kotlin" %}
```kotlin
val sdk: JustTrackSdk = JustTrack.getInstance()
sdk.forwardAdImpression(
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
{% endtab %}
{% endtabs %}

This method accepts an `AdImpression` whose parameters are:

* **adFormat**: The format of the ad.
* **adSdkName**: The name of the SDK you used to fill the ad space, for example "ironsource" or "admob". When using ad mediation, this is the name of the mediation platform.

{% hint style="info" %}
The SDK name must be **lowercase**. So, for example, you would use "ironsource", not "Ironsource".
{% endhint %}

Additionally, you can use the following methods to set more dimensions:

| Method               | Argument                                                                                                                            | Acceptable values                                                                                       |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| `.setNetwork()`      | The name of the ad network that provided the ad. When using ad mediation, this is the ad network that won the bid for the ad space. | String value or null.                                                                                   |
| `.setPlacement()`    | The placement of the ad.                                                                                                            | String value or null.                                                                                   |
| `.setTestGroup()`    | The test group of the user, if you are A/B testing.                                                                                 | String value or null.                                                                                   |
| `.setSegmentName()`  | The name of the segment of the ad.                                                                                                  | String value or null.                                                                                   |
| `.setInstanceName()` | The name of the instance of the ad.                                                                                                 | String value or null.                                                                                   |
| `.setBundleId()`     | The bundleId for the app being advertised.                                                                                          | String value or null.                                                                                   |
| `.setRevenue()`      | The amount of revenue this ad generated.                                                                                            | Money object with a non-negative amount. The currency must be a three-letter uppercase ISO 4217 string. |

Upon success `.forwardAdImpression()` returns true. If a parameter is invalid, false is returned.

