# Connect a custom network

While justtrack offers many built-in [networks](broken-reference) for you to use with your application, you may need to connect a custom network we don't yet support. You can connect a custom network with just five steps using our Network Wizard.

## Before you begin

Only **admins** and **managers** can create and edit networks. So, to complete the steps in this guide, you must first be an admin or a manager for your company.

{% hint style="info" %}
Learn more about these roles in [User Roles and Permissions](../user-management/user-roles-and-permissions.md).
{% endhint %}

## Open the Network Wizard

In the _Main Menu_, click [**Admin -> Networks**](https://dashboard.justtrack.io/admin/networks):

<figure><img src="../.gitbook/assets/Screenshot 2023-09-18 at 16.33.52.png" alt="" width="563"><figcaption><p>Networks</p></figcaption></figure>

Then, click **Connect Network**:

<figure><img src="../.gitbook/assets/Screenshot 2023-09-18 at 16.34.54.png" alt="" width="563"><figcaption><p>Connect Network</p></figcaption></figure>

This opens the Network Wizard where you'll connect a network to your company. In this guide, you learn how to connect a custom network.

## Connect a custom network

In the Network Wizard, click **+:**

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 12.08.46.png" alt="" width="563"><figcaption><p>Custom Network</p></figcaption></figure>

This opens the _Network Details_ page where you'll input the following attributes:

| Attribute               | Description                                                                    |
| ----------------------- | ------------------------------------------------------------------------------ |
| Name                    | The name of the custom network                                                 |
| Channel                 | The default [channel](broken-reference) to use for campaigns for this network. |
| Spend Currency          | The currency for your marketing budget                                         |
| Multi country campaigns | Whether or not the network supports campaigns in multiple countries            |

{% hint style="info" %}
If your network's default channel is not included in the options, [create a new channel](../channel-management/manage-your-channels.md#create-a-channel).
{% endhint %}

Fill in the details for your network, and click **Next**.

## Set up your tracking URL

On the _Tracking_ page, you'll configure your [tracking URLs](broken-reference):

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 13.46.31 (1).png" alt=""><figcaption></figcaption></figure>

Here, you configure the [parameters](broken-reference) for two tracking URLs, one for impressions (views) and one for clicks, using the following fields:

| Attribute       | Description                                                                                                                                                                                                                                                                                 |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Parameter Name  | The name of the parameter you'll use in justtrack                                                                                                                                                                                                                                           |
| URL Placeholder | The placeholder to be used in the query-string. For [justtrack parameters](broken-reference), this value isn't important. For [network parameters](broken-reference), this is the name your network uses to refer to the corresponding parameter. Check their documentation for this value. |
| Views           | This sets the parameter in the impressions URL                                                                                                                                                                                                                                              |
| Clicks          | This sets the parameter in the clicks URL                                                                                                                                                                                                                                                   |

{% hint style="info" %}
You can hardcode some of these parameter values, but most will be dependent on the network, campaign, and user. For these, you use [placeholders](broken-reference).
{% endhint %}

The Network Wizard automatically shows some parameters, but if you want to see more, click **Select new**:

<figure><img src="../.gitbook/assets/Screenshot 2023-10-02 at 13.46.31.png" alt="" width="563"><figcaption><p>New Parameter</p></figcaption></figure>

Now, choose the parameter you want to track, customise the placeholder, and select which URLs will include your parameter. Add as many parameters as you need, then click **Next**.

## Confirm your network connection

In this last step, you'll confirm all the settings you configured for your custom network. When you're ready, click **Connect.**

## Configure your postbacks

When you've connected your network, you'll land on the _Network Edit_ page. Here, you'll configure a [postback](broken-reference) for each of your company's [goals](broken-reference):

<figure><img src="../.gitbook/assets/Screenshot 2023-10-04 at 11.14.51.png" alt="" width="563"><figcaption><p>Configure Postbacks</p></figcaption></figure>

First, choose the ATTRIBUTED or NON-ATTRIBUTED tab, depending on which type of postback you'd like to configure. Then, click **Add Postback.** This opens a modal for you to configure a postback.

The attributes for attributed postbacks are:

| Attribute        | Description                                                                                                                               |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Status           | This determines whether we should send the postback (active) or not (inactive)                                                            |
| App              | This selects the app for which you want to send this postback.                                                                            |
| Goal             | We send a postback to the network when users trigger this goal                                                                            |
| Custom Goal Name | This lets you override the `{goalName}` parameter value.                                                                                  |
| Postback URL     | We send the postback to this URL. Each URL can have [placeholder parameters](broken-reference) that are filled when we send the postback. |

The attributes for non-attributed postbacks are:

| Attribute                     | Description                                                                                                                               |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Status                        | This determines whether we should send the postback (active) or not (inactive)                                                            |
| App                           | This selects the app for which you want to send this postback.                                                                            |
| Goal                          | We send a postback to the network when users trigger this goal                                                                            |
| Include attributed users from | This selects the networks for which you want to send this postback for attributed users.                                                  |
| Include fraud users from      | This selects the networks for which you want to send this postback for fraud users.                                                       |
| Custom Goal Name              | This lets you override the `{goalName}` parameter value.                                                                                  |
| Postback URL                  | We send the postback to this URL. Each URL can have [placeholder parameters](broken-reference) that are filled when we send the postback. |

Add your postback, then click **Save**. Repeat this step for all your goals.&#x20;

## **Conclusion**

You're done! You've connected a custom network to your company. You'll see it in [**Admin -> Networks**](https://dashboard.justtrack.io/admin/networks) in the _Main Menu_.

From here, you can do things like:

* Edit the network.
* Copy your tracking URLs.
* Configure new postbacks.

