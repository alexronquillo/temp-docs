# Postbacks

A **postback** is when we send attribution data to inform a network about user events:

<figure><img src="../.gitbook/assets/Screenshot 2023-09-19 at 15.26.44.png" alt=""><figcaption><p>Postback Flow</p></figcaption></figure>

1. When a user installs your app or triggers an in-app event, your app sends data to your account in justtrack, using our SDK.
2. When those events match certain goals for which you've defined postbacks, we send attribution data to the network.

{% hint style="success" %}
**Example:** Imagine a user sees an ad that's managed by Adjoe, and they click the ad and install your app. In this case, our SDK reports the install to justtrack, attributing the install to Adjoe. When we receive that information from the SDK, we share that attribution with Adjoe, letting them know that the campaign led to the install.
{% endhint %}

Communicating with networks like this is important because they use it to analyse the efficacy of their platform and charge you accurately for their service.

{% hint style="info" %}
The address where we send this data is called a **postback URL**. Because these are network-specific, you'll need to look up their URL structure in their documentation.
{% endhint %}

### Goal-based Postbacks

In justtrack, postbacks are based on [goals](broken-reference). For every goal your app has, you can configure a network postback URL. When a goal is triggered, we use the corresponding postback URL to send data to your connected network, informing them of the user behaviors that originated from their ad.

Every time you configure a network, we automatically create a postback for the **Install** goal for you. For all other goals, you must decide if you want to manually create a postback.

{% hint style="warning" %}
Make sure to activate your postbacks or we won't use them to send data to your connected network.
{% endhint %}

### Parameters

You use postback parameters to specify the attribution data you want to send to the network. For example, you might want to include the app id or the user's country. Like [tracking URLs](broken-reference), you specify parameter names and corresponding placeholders. When a user triggers an app goal, we send a postback, replacing the placeholders with real values.

{% hint style="info" %}
For many networks, we've already created postbacks with parameters for you.
{% endhint %}

Here is an example postback URL:

```
https://postback.adnet.com?advertisingId={mobileId}&countryCode={country}
```

In this example, you have two parameters:

* `advertisingId`: Uses the `{mobileId}` placeholder to send the Identifier for Advertising.
* `countryCode`: Uses the `{country}` placeholder to send the user's country.

For a list of available parameters, consult your ad network's documentation. Here is a list of all placeholders we support:

| Placeholder             | Description                                                                                                                                                                                    |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `{clickId}`             | Network generated unique ID of the click                                                                                                                                                       |
| `{viewId}`              | Network generated unique ID of the view                                                                                                                                                        |
| `{sourceId}`            | ID of the publisher’s app in which the ad was shown                                                                                                                                            |
| `{sourceName}`          | Name of the publisher’s app in which the ad was shown                                                                                                                                          |
| `{sourceBundleId}`      | App bundle ID/package name of the publisher’s app in which the ad was show                                                                                                                     |
| `{goalId}`              | ID of the reached goal                                                                                                                                                                         |
| `{goalName}`            | IName of the reached goal                                                                                                                                                                      |
| `{goalIdentifier}`      | ID of the goal and app. Can be configured on Postbacks for each app for networks that require an ID on goal and app level.                                                                     |
| `{storeId}`             | Store ID of the advertiser’s app                                                                                                                                                               |
| `{appBundleId}`         | Package name/Track ID of the advertiser’s app                                                                                                                                                  |
| `{appId}`               | Internal ID of the advertiser’s app                                                                                                                                                            |
| `{conversionDateIso}`   | Time of the app install in ISO 8601, _estimated for iOS 14_                                                                                                                                    |
| `{conversionDateTime}`  | Time of the app install in YYYY-MM-DD HH:MM:SS                                                                                                                                                 |
| `{conversionTimestamp}` | Unix timestamp of the app install (seconds precision)                                                                                                                                          |
| `{attribution}`         | Information if a user was attributed by referrer, GAID/IDFA, _SKAdNetwork_, etc.                                                                                                               |
| `{attributionType}`     | "view" or "click" based on the attribution type                                                                                                                                                |
| `{attributionProvider}` | Attribution provider name                                                                                                                                                                      |
| `{isViewAttribution}`   | "1" in case of view attribution and "0" in case of click attribution                                                                                                                           |
| `{isAttributed}`        | "1" when attributed to notified network and "0" when attributed to other networks or organic                                                                                                   |
| `{userType}`            | User type can either be "acquisition" (new users) or "retargeting" (returning users)                                                                                                           |
| `{campaignType}`        | Campaign type can either be "acquisition" or "retargeting"                                                                                                                                     |
| `{eventDateIso}`        | Time of event in ISO 8601                                                                                                                                                                      |
| `{eventDateTime}`       | Time of event in YYYY-MM-DD HH:MM:SS                                                                                                                                                           |
| `{eventTimestamp}`      | Event Unix timestamp (seconds precision)                                                                                                                                                       |
| `{eventValue}`          | <p>Value of the event as a float with 6 decimal places.<br>For revenue events this is the revenue value in USD.<br>For events that have no value attached to them this is always 0.000000.</p> |
| `{sourceCampaignId}`    | Campaign ID of the network as provided in the tracking links _or as provided by SKAdNetwork Postback_                                                                                          |
| `{mobileId}`            | Google Advertiser ID (GAID) / Identifier for Advertisers (IDFA)                                                                                                                                |
| `{deviceId}`            | Android Device ID / Identifier for Vendors (IDFV)                                                                                                                                              |
| `{androidId}`           | Android Device ID, empty on iOS                                                                                                                                                                |
| `{idfv}`                | Identifier for Vendors (IDFV), empty on Android                                                                                                                                                |
| `{limitedAdTracking}`   | "1" if ad tracking is limited "0" if ad tracking is not limited                                                                                                                                |
| `{ip}`                  | Current GEO IP of the tracking event                                                                                                                                                           |
| `{country}`             | GEO country of the user (ISO3166 alpha-2)                                                                                                                                                      |
| `{city}`                | GEO city of the user                                                                                                                                                                           |
| `{platform}`            | "android" or "ios"                                                                                                                                                                             |
| `{osVersion}`           | Operating system version                                                                                                                                                                       |
| `{deviceType}`          | Device type as defined by Google                                                                                                                                                               |
| `{deviceModel}`         | Device model as defined by Google                                                                                                                                                              |
| `{device}`              | Device name as defined by Google                                                                                                                                                               |
| `{userAgent}`           | User agent of the tracking event                                                                                                                                                               |
| `{currentDateIso}`      | Current time in ISO 8601                                                                                                                                                                       |
| `{currentDateTime}`     | Current time in YYYY-MM-DD HH:MM:SS                                                                                                                                                            |
| `{currentTimestamp}`    | Current time as Unix timestamp (seconds precision)                                                                                                                                             |
| `{network}`             | Network user has been attributed to                                                                                                                                                            |
| `{channel}`             | Channel defined via justtrack dashboard                                                                                                                                                        |
| `{campaignId}`          | JustTrack internal campaign ID                                                                                                                                                                 |
| `{appUserId}`           | JustTrack internal ID of the user                                                                                                                                                              |
| `{custom0}`             | Optional custom parameter                                                                                                                                                                      |
| `{custom1}`             | Optional custom parameter                                                                                                                                                                      |
| `{custom2}`             | Optional custom parameter                                                                                                                                                                      |
| `{custom3}`             | Optional custom parameter                                                                                                                                                                      |

{% hint style="warning" %}
The user-specific parameters are not available on iOS 14 SKAdNetwork integrations due to Apple's privacy regulation. Refer to the [SKAdNetwork documentation](https://developer.apple.com/documentation/storekit/skadnetwork/identifying\_the\_parameters\_in\_install-validation\_postbacks) for postback details.
{% endhint %}

Some placeholders are network-specific. We can provide these values in a postback after you set them in your app configuration:

| Postback Parameter      | Description                  |
| ----------------------- | ---------------------------- |
| `{digitalTurbineAppId}` | Network and app specific Id  |
| `{fyberAppId}`          | Network and app specific Id  |
| `{kayzenApiKey}`        | Network and app specific Key |

### Attributed vs. Non-attributed Postbacks

You can send postbacks to a network whether a user's behavior is attributed to that network or not.&#x20;

* If the user behaviors _are_ attributed to that network, we call these **attributed postbacks**.&#x20;
* If the user behaviors _are not_ attributed to that network, we call these **non-attributed postbacks**.&#x20;

Non-attributed postbacks can come from organic users (attributed to no network) or users who are attributed to a different network.

There are two primary reasons why non-attributed postbacks are valuable to send:

1. Sharing installs Increases eCPM over your advertising networks, as they can suppress further ads to already installed users
2. With post-install events, ad networks build lookalikes/audiences and can analyze what makes a user valuable to the customer and optimize towards targeting similar users

## Learn more about Postbacks

* [Connect a Custom Network](broken-reference)
* [Tracking Documentation](broken-reference)
