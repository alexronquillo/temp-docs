# Apple App Store

## App Store in-app purchase validation

To ensure we don't count canceled or duplicated in-app purchases forwarded from your app, we validate each purchase on backend side. For iOS apps you have to enter a 32 character hexadecimal shared secret on the app configuration page on the justtrack dashboard. Using this secret, we then can accurately track purchases made by your users and display the correct revenue for your app.

You can configure a global shared secret for your account as well as an app-specific shared secret per app. The global shared secret will only be used if no app-specific secret is configured. This way, you can either setup a single global shared secret (if you have all your apps in a single account) or setup the correct shared secrets as needed (if you for example have more than one account managing your apps with Apple).

### Global shared secret

The global shared secret can be found at "Users and Access" below the point "Shared Secret". If no shared secret is not yet setup, just generate a new shared secret. Afterwards, you should see your shared secret like this:

<figure><img src="../../.gitbook/assets/App Store Global Shared Secret.png" alt=""><figcaption><p>Global shared secret for your App Store Connect account.</p></figcaption></figure>

### App-specific shared secret

If you already have a global shared secret configured, you normally don't need to add an app-specific shared secret. However, if you can't share the global secret with justtrack or are using more than one account, you need to configure an app-specific shared secret.

To create an app-specific shared secret, select "App Information" for your app, find the entry "App-Specific Shared Secret" and click on "Manage".

<figure><img src="../../.gitbook/assets/App Specific Secret 1.png" alt=""><figcaption><p>Location of the app-specific shared secret</p></figcaption></figure>

If you don't have an app-specific shared secret configured, you will now be presented with a dialog to generate one:

<figure><img src="../../.gitbook/assets/App Specific Secret 2.png" alt=""><figcaption><p>Generating an app-specific shared secret</p></figcaption></figure>

Once you generated the app-specific shared secret, you will be presented with the 32 character hexadecimal string which you can enter on the justtrack dashboard.

<figure><img src="../../.gitbook/assets/App Specific Secret 3.png" alt=""><figcaption><p>App-specific shared secret</p></figcaption></figure>

### Setting up shared secrets on the justtrack dashboard

To get your in-app purchases verified and tracked by justtrack you need to enter the (global or app-specific) shared secret for your app on the justtrack dashboard. To do so, navigate to apps, select your iOS app and enter edit mode.

<figure><img src="../../.gitbook/assets/Setup Secret 2.png" alt=""><figcaption><p>Editing an app to configure shared secrets</p></figcaption></figure>

Now you will see two text fields in which you can enter either the shared secret for your App Store Connect account (the global shared secret) or your app-specific secret. You only need to enter an app-specific shared secret if you can't or don't want to enter the global shared secret, your app already has an app-specific shared secret on App Store Connect, or if your app uses a different global shared secret than the global secret you entered (because you have more than one app in more than one App Store Connect account - in this case, you have to generate an app-specific shared secret on App Store Connect for your app).

<figure><img src="../../.gitbook/assets/Setup Secret 4.png" alt=""><figcaption><p>Configuring an app-specific as well as global shared secret</p></figcaption></figure>

One you save your app, you should now see the shared secrets you configured for your app. You can now start forwarding in-app purchases from your app and will see the revenue you make from them on the justtrack dashboard.

<figure><img src="../../.gitbook/assets/Setup Secret 5.png" alt=""><figcaption><p>An app-specific as well as a global shared secret configured for an app and account</p></figcaption></figure>

### Forwarding in-app purchase events

After setting up the credentials for your app(s), you can now start forwarding in-app purchases from your app. You can find more information about this in our [iOS](broken-reference) and [Unity](broken-reference) SDK documentation.
