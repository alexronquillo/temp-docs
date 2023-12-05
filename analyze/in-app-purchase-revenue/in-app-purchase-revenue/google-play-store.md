# Google Play Store

## Play Store in-app purchase validation

To ensure we don't count canceled or duplicated in-app purchases forwarded from your app, we validate each purchase on backend side. For Android apps you have to provide us with the credentials file of a Play Store service account. The service account provides an application instead of a user access to the Google Play Developer Publishing API. Using this access, we then can accurately track purchases made by your users and display the correct revenue for your app.

You can configure a global service account for all your apps on the justtrack dashboard as well as app-specific service accounts. The global account will then only be used if no app-specific account is configured. Using app-specific accounts are useful if you have different Play Store accounts for your apps and thus can't setup a single service account for all of them.

### Creating a service account

Open the [Google Play Developer Console](https://play.google.com/apps/publish/) and navigate to the **Settings** section. Then select the **API access** entry from the **Developer account** section.

<figure><img src="../../.gitbook/assets/Setup Play Console 1.png" alt=""><figcaption><p>Granting API access to your Play Console account</p></figcaption></figure>

Click the **Choose a project to link** button and agree to the terms of service.

<figure><img src="../../.gitbook/assets/Setup Play Console 2.png" alt=""><figcaption><p>Agreeing to the Terms of Service</p></figcaption></figure>

Select the **Link existing project** option, select **Google Play Android Developer** from the drop-down and click **Link project**.

<figure><img src="../../.gitbook/assets/Setup Play Console 3.png" alt=""><figcaption><p>Linking with an existing Google Cloud project</p></figcaption></figure>

{% hint style="info" %}
If you have not created a Google Cloud project for your app already, you have to select **Create new project** instead. After creating a new project, it should already be linked. If this is not the case, you have to link it manually.
{% endhint %}

At the bottom of the page, click the **Create new service account** button and click the link to [**Google Cloud Platform**](https://console.cloud.google.com/iam-admin/serviceaccounts) from the dialog. On the Google Cloud page, click on the **Create Service Account** button:

<figure><img src="../../.gitbook/assets/Create Service Account.png" alt=""><figcaption><p>Create a new service account for your project</p></figcaption></figure>

Set a name for your service account:

<figure><img src="../../.gitbook/assets/Name Service Account.png" alt=""><figcaption><p>Creating a new service account</p></figcaption></figure>

In the next step, select the **Monitoring Viewer** role:

<figure><img src="../../.gitbook/assets/Role Service Account.png" alt=""><figcaption><p>Configure the service account</p></figcaption></figure>

After creating the service account, select the account, go to the **Keys** tab and select **Create new key**:

<figure><img src="../../.gitbook/assets/Keys Service Account.png" alt=""><figcaption><p>Create a new key for your service account</p></figcaption></figure>

Create the key in **JSON** format. Once you create the key, it should get downloaded automatically to your computer. You have to upload this file later on the justtrack dashboard.

<figure><img src="../../.gitbook/assets/Create Key Service Account.png" alt=""><figcaption><p>Creating a new key for your service account</p></figcaption></figure>

### Grant the service account access to your apps

After creating the service account, you still need to grant it permission on the Google Play Console. Navigate again to **API access**. You should find your service account listed now with a link to manage the permissions of the account:

<figure><img src="../../.gitbook/assets/Setup Play Console 4.png" alt=""><figcaption><p>The service account is listed on the Google Play console</p></figcaption></figure>

After clicking said link, you need to ensure the account has the following permissions:

* View app information (read only)
* View financial data
* Manage orders and subscriptions

Once everything is setup correctly, click **Invite user**:

<figure><img src="../../.gitbook/assets/Setup Play Console 5.png" alt=""><figcaption><p>Setting up the correct permissions for your service account</p></figcaption></figure>

### Setting up the service account on the justtrack dashboard

To get your in-app purchases verified and tracked by justtrack you need to upload the JSON file you received when you created the key on the justtrack dashboard. To do so, navigate to apps, select your Android app and enter edit mode.

<figure><img src="../../.gitbook/assets/Setup Secret 2 Android.png" alt=""><figcaption><p>Editing an app to configure shared secrets</p></figcaption></figure>

You will see two buttons to upload the key file for your service account. You need to upload it either as the key just for this app or you can upload it as the default key for all apps which don't have an app-specific key configured.

<figure><img src="../../.gitbook/assets/Setup Secret 4 Android.png" alt=""><figcaption><p>Uploading an app-specific or global key file</p></figcaption></figure>

Once you uploaded the file and saved your app at the bottom of the page, you should now see the key configured for your app (or all your apps, if you uploaded it as a global key). You can now start forwarding in-app purchases from your app and will see the revenue you make from them on the justtrack dashboard.

<figure><img src="../../.gitbook/assets/Setup Secret 5 Android.png" alt=""><figcaption><p>Global service account configured</p></figcaption></figure>

{% hint style="info" %}
It can take up to 48 hours until the permissions configured for your new service account got propagated on Google's internal systems. In this case, it might take a while until you will see first in-app purchase revenue for your app.
{% endhint %}

### Forwarding in-app purchase events

After setting up the credentials for your app(s), you can now start forwarding in-app purchases from your app. You can find more information about this in our [Android](broken-reference) and [Unity](broken-reference) SDK documentation.
