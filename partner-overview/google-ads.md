# Google Ads

Justtrack supports the following UA automation and optimization features, which need to be set up individually:

* Cost Integration
* Bid Management
* Campaign Management (creation and adjustments of attributes and targeting options)
* Creative Management

### Cost Integration, Bid Management, Campaign Management

The required credentials need to be entered in the `Management` Section of Google Ads credentials page.

You need to do 3 main things to be able to see all the data in justtrack and use all automation features:

1. Enable the Google Ads API
2. Use Google's OAuth 2.0 Authentication flow to get the required credentials
3. Enter developer token and app IDs

#### 1. Enable the Google Ads API

If the API is not enabled yet, please navigate to [this URL](https://console.developers.google.com/apis/api/googleads.googleapis.com/overview?project={your\_project\_id}) (exchange the project id with your project id) and enable the API.

Navigate to `APIs & Services`, then `Enable APIs & Services`. Search for Google Ads API and select it. Then click `Enable`.

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

#### 2. Get the required OAuth credentials

To retrieve the required credentials and enter them in the justtrack network credentials tab, please follow these steps:

1. Go to: [https://console.cloud.google.com/apis/credentials ](https://console.cloud.google.com/apis/credentials)to create an "`OAuth client ID`" of type "`Web application`".
2. Use the [redirect uri ](https://developers.google.com/oauthplayground)and turn this into a refresh token with AdWords API scope [here](https://developers.google.com/oauthplayground/):\
   Click the gear icon and enable "`Use your own OAuth credentials`". Enter your client id and client secret from the first step and click "close". On the left side below step 1 expand "`AdWords API`".
3. Now tick the entry "`https://www.googleapis.com/auth/adwords`" and click "`Authorize APIs`".\
   On the Google consent screen choose the account that has access to your ad campaigns. You should now have landed back in the OAuth2 Playground and an "`Authorization code`" should be filled into the Step 2 "`Authorization code`" field. Click "`Exchange authorization code for tokens`" to fetch the refresh token. Copy the refresh token.

{% hint style="info" %}
The `Grant Type` needs to be `refresh_token`.
{% endhint %}

#### 3. Provide additional credentials

Additionally, you need to enter a `Developer Token` to be able to use these features. You can get it by navigating to `Tools & Settings` in the Google Ads dashboard. Then click on `API Center`.

The `Login Customer ID` is needed if your access to the customer account is through a manager account. This attribute must be set to the customer ID of the manager account. You can find the ID when you click on Help in the Google Ads dashboard.

As a last step, please navigate to the product section of justtrack and enter the `ClientCustomerId` for your apps. It is needed to use justtrack's bid manager. This attribute can be found in your Google Ads Account right next to the selected app:

![Your app with the relevant id](<../.gitbook/assets/Bildschirmfoto 2022-07-11 um 14.14.26.png>)

If you open the dropdown, you will see the ids for other apps in your account.

{% hint style="warning" %}
Bid adjustments or campaign adjustments cannot be done for apps where this attribute is not set. You will receive a notification in case it is missing.
{% endhint %}

### Creative Management
