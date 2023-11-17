# ironSource Mediation

When enabled on the ironSource dashboard, justtrack receives revenue estimates in real-time. This allows you to see the performance results and derive actions from it immediately. In a second step, justtrack verifies the estimates with ironSource the next day at 2 pm UTC. The estimates will then automatically be updated.

Moreover, the justtrack SDK automatically tracks whenever an ad is successfully shown via the ironSource mediation. This happens in real time and automatically. Included are banner, interstitial, rewarded ad and offerwall impressions.

{% hint style="danger" %}
**Do not limit the use of user data** via the ironSource dashboard. Please set the app settings to:

* COPPA: This app is partially directed towards children"
* CCPA: "Do not restrict the use of user data"

Limiting the use of user data will prevent ironSource revenue being availble on the justtrack dashboard.
{% endhint %}

{% hint style="info" %}
Revenue from the previous day becomes available via the ironSource API at 2 pm UTC. We then automatically import this data.
{% endhint %}

In order for the revenue to get imported, you need to add your ironSource credentials to the ironSource integration for your app. You need at least the following values:

* Secret Key
* Refresh Token

You can find the credentials in the account settings on the Ironsource dashboard.

![](<../../.gitbook/assets/Ironsource Credentials.png>)

Please enter the credentials for each app's ironSource integration in the justtrack Admin area.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The configuration is entirely on app level - which means you have to repeat it on every single app. This allows you to use different ironSource accounts for monetization across different apps.
{% endhint %}

Moreover, the justtrack SDK automatically tracks whenever an ad is shown via the ironSource mediation. This happens in real time and automatically. All you need to do is to make the justtrack SDK initialize the ironSource SDK and enable revenue measurements (ARM) SDK postbacks via the Ironsource account settings.

### Java Integration

The Java justtrack SDK needs to integrate itself with the ironSource SDK before the latter is initialized. It will register the required listeners and forward the justtrack user id to the ironSource SDK. After this step is done, you need to initialize the ironSource SDK as you would have normally done:

```java
JustTrackSdk sdk; // needs to be retrieved from somewhere, omitted from the example
Future<?> integration = sdk.integrateWithIronSource();
try {
    integration.get();
    // the JustTrack SDK successfully integrated with the ironSource SDK
} catch (Exception e) {
    // there was an error integrating with the ironSource SDK
}
// initialize the ironSource SDK in any case
IronSource.init(
    activity,
    "abcd1234",
    IronSource.AD_UNIT.REWARDED_VIDEO,
    IronSource.AD_UNIT.INTERSTITIAL,
    IronSource.AD_UNIT.BANNER
);
```

`integrateWithIronSource` returns a `Future` which resolves as soon as the integration with ironSource succeeded. In the example, we wait for it until it either resolves or fails with an exception. Afterwards we can proceed with initializing the ironSource SDK. Keep in mind that you should not wait for the future on the main thread (it would block the UI and make your app unresponsive).

### Unity Integration

The Unity justtrack SDK can take care for you to completely initialize the Unity ironSource SDK. It is necessary that the ironSource SDK is only initialized after the justtrack SDK has setup the required listeners and forwarded the justtrack user id to it. If the ironSource SDK is initialized earlier, the justtrack SDK can't track ad impressions and the revenue data might not be imported as precisely (especially on iOS if the IDFA of a user is not available).

Using the prefab for the justtrack SDK, you can scroll to the ironSource integration section, add your app key (`abcd1234` in the example), and select the ad units you want to have available. You have to configure the integration for Android and iOS separately.

![](<../../.gitbook/assets/image (5).png>)

It can take a few seconds until the justtrack SDK has initialized the ironSource SDK (as it needs to talk to the justtrack backend in some cases). If you need to know whether the ironSource SDK is already safe to use, you can query `JustTrackSDKBehaviour.IronSourceInitialized` for the current status of the initialization. If you definitely want to run some code as soon as ironSource has been initialized (for example, to display an ad) you can use `JustTrackSDKBehaviour.OnIronSourceInitialized` to schedule an action to be executed as soon as that happened. If the ironSource SDK has already been initialized your callback will also be executed a single time.

```csharp
using JustTrack;

JustTrackSDKBehaviour.OnIronSourceInitialized(() => {
    // ironSource has now been initialized
    bool isInitialized = JustTrackSDKBehaviour.IronSourceInitialized; 
    // isInitialized is always true
});
```

The above code shows how to submit a callback to be called as soon as the ironSource SDK has been executed. It will always execute the callback once and the ironSource SDK will always be initialized when the callback is called.
