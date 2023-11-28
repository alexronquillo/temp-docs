---
description: Set up Unity as an ad network
---

# Unity

Unity is a video ad network. When you set up Unity as an ad network for justtrack, the following configuration will already be automatically set up:

* Tracking links and the URL placeholders
* Postbacks
* SKAd network id
* Automated campaign creation based on clicks and views

Justtrack also supports the following UA automation and optimization features, which need to be set up individually:

* Cost Integration
* Bid Management
* Campaign Management (creation and adjustments of attributes and targeting options)
* Creative Management

### Cost Integration

We are integrated with Unity's [Advertising Statistics API](https://services.docs.unity.com/statistics/v1/index.html). This requires an API-Key for authentication. Please retrieve the API Key in the Growth section of your account in API Management and paste in in the Unity's credentials tab in justtrack's network page.

<figure><img src="../../.gitbook/assets/unity-cost-apikey (1).png" alt=""><figcaption><p>Copy the API Key for the Stats API Access</p></figcaption></figure>

{% hint style="warning" %}
The API key is generated for a specific account or username. If that account is removed from the organization, that API key will be automatically revoked. That is why we suggest creating a separate justtrack user.
{% endhint %}

### Bid, Creative and Campaign Management

Justtrack is integrated with Unity's [API Management](https://services.docs.unity.com/advertise/v1/index.html) to be able to automate your workflows. The required authentication is done via a service account. Please navigate to `Organization Settings` --> `Service Accounts`. If no service account was created, please create one and associate a `Key`. Copy this `Key` and paste it to the field `Key ID` in the credentials tab in justtrack's network page.

<figure><img src="../../.gitbook/assets/unity-service-accounts (1).png" alt=""><figcaption><p>Copy the service account's Key and paste it in justtrack</p></figcaption></figure>

{% hint style="warning" %}
The service account needs to have the correct permissions configured. If e.g. you want to use campaign management via justtrack, the service account needs to have access to the `Advertise API Campaigns Editor`.

You can find Unity's specification here: [https://services.docs.unity.com/advertise/v1/index.html#section/Authentication/Roles-and-Permissions](https://services.docs.unity.com/advertise/v1/index.html#section/Authentication/Roles-and-Permissions)
{% endhint %}

<figure><img src="../../.gitbook/assets/Unity-Service-Accounts-Roles-Permissions (1).png" alt=""><figcaption><p>Unity Service Account Roles and Permissions</p></figcaption></figure>

Additionally, this integration requires a number of attributes:

* `campaignSetId`
* `GameId`
* `organizationId`
* `organizationCoreId`

`campaignSetId` and `GameId` are app specific parameters and need to be entered for each app. Navigate to the Product Page and enter the attributes for each app. The attributes can also be entered directly on app creation.

`organizationId` and `organizationCoreId` are unique to your account and is retrieved automatically by justtrack. You can find it by navigating to your Organization Settings in the Growth tab of Unity's dashboard.

<figure><img src="../../.gitbook/assets/unity-orgIds (1).png" alt=""><figcaption><p>organizationId and coreOrganizationId</p></figcaption></figure>

`organizationId` is required for services like bid adjustments, campaign and creative management.

`organizationCoreId` is required for cost integration.

#### Campaign Set ID

Please retrieve the `campaignSetId` either via

1. the Unity dashboard Apps page: `https://dashboard.unity3d.com/organizations/`**`<your-organization-id>`**`/acquire/campaign-sets`
2. from a campaign link: `https://dashboard.unity3d.com/organizations/`**`<your-organization-id>`**`/acquire/campaign-sets/<`**`campaignsetid>`**`/campaigns/`**`<campaignid>`**
3. copying it from the Apps page directly:

![App Overview in Apps Page with Game ID, Campaign Set Id and Store ID. Click on copy to copy the value.](<../../.gitbook/assets/unity-campaignsetid (1).png>)

#### Game ID

Please retrieve the `gameId` via copying it from the Apps page directly as shown in the screenshot above.

{% hint style="warning" %}
**Important Note:** If any of these app-specific attributes are not configured in justtrack, services such as campaign management or bid adjustments will not work.

If you use these features without the necessary attributes being provided, the action cannot be executed and will error. You will get a notification which will direct you to the attributes that need to be provided.
{% endhint %}
