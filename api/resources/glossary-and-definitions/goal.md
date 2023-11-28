# Goal

With **Goals**, you can track and report certain behaviors that users take in your application. They group information about an event with extra details about how users trigger that event. These extra details include:

* Conditions that filter out irrelevant instances of the event.
* The number of times the goal is triggered for the event.

Together, this information records events with specific constraints so you can establish patterns, analyse user behaviours, and inform networks.

{% hint style="info" %}
**Limitation:** Each company can only have _25_ goals.
{% endhint %}

## Using Goals

You use goals in a few places within the marketing pipeline:

<figure><img src="../../.gitbook/assets/Screenshot 2023-09-19 at 15.21.41.png" alt=""><figcaption><p>Goal Flow</p></figcaption></figure>

1. First, when you create a campaign with a network, you may assign it a goal. For example, you might have a goal for users to install your app. Or, you might have a goal for users to make an in-app purchase.
2. When users view or click your ad, the network sends data to your [tracking URL](../../../resources/glossary-and-definitions/broken-reference/) that includes a `goalId`.
3. After that, users are redirected to your application where they may trigger some events. The justtrack SDK sends those events to your account so you can analyse them.
4. If those events match one of your goals and you have an active [postback](../../../resources/glossary-and-definitions/broken-reference/) configured for that goal, we trigger the postback to send attribution data to the network that ran the source campaign.

{% hint style="info" %}
**Why have a goal for your campaign?** Usually, you only pay your network for a certain "conversion event". Therefore, we need to know what that event is. This way, we can calculate your marketing spend after we send the postback for that goal.
{% endhint %}

## Learn more about Goals

* [Connect a custom network](../../../resources/glossary-and-definitions/broken-reference/)
