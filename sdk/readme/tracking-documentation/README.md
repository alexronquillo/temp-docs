# Tracking Documentation

This documentation describes how Tracking and Attribution works for both Android and iOS with the justtrack SDK.

**In general, we do a last click/last view attribution. In order to find the best possible match between a click/view and an install, we support the following attribution practices (available both `s2s` and `non-s2s`):**

* Referrer for Android
* Device id based - GAID for Android and IDFA for iOS (prior to iOS 14)
* Probabilistic fingerprinting in accordance with Apple's guidelines for iOS 14
* SKAdNetwork for iOS 14
* Postbacks from other attribution providers

{% hint style="info" %}
We use a scoring logic that allows us to determine the most likely click, view or postback that caused an install.

During this process, we value the **Playstore referrer**, **GAID** and **IDFA** as the strongest signals. If they are missing, we do probabilistic fingerprinting and take additional parameters like IP, device type, device resolution and more into account.
{% endhint %}

Please check the specifications for each platform in the individual subsections for [Android](android.md) and [iOS](skadnetwork-for-ios.md).

## Tracking URLs and Postbacks

Here, you can read more about [tracking URLs](https://app.gitbook.com/s/4favyoz2l7ENoW5stOlK/glossary-and-definitions/tracking-url) and [postbacks](https://app.gitbook.com/s/4favyoz2l7ENoW5stOlK/glossary-and-definitions/postbacks), including how they work and what parameters are available.
