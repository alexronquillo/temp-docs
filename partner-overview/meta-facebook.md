# Meta / Facebook

Justtrack supports the following UA automation and optimization features, which need to be set up individually:

* Cost Integration
* Bid Management
* Campaign Management (creation and adjustments of attributes and targeting options)
* Creative Management

## Attribution

#### **App ID** <a href="#app-id" id="app-id"></a>

1. 1.Open the[ Meta for Developers.](https://developers.facebook.com/apps)
2. 2.Choose your App and Open it. You need to have the **Developer** Role.
3. 3.Open **Settings** > **Basic** in the navigation.
4. 4.You will find the **App ID** at the top of the page.

![Facebook App ID](<../.gitbook/assets/Facebook App ID.png>)

#### **Install Referrer Decryption Key** <a href="#install-referrer-decryption-key" id="install-referrer-decryption-key"></a>

App-specific key to decrypt Facebook last-click campaign metadata provided on app install on Google Play's Install Referrer. Unique per application.

* Open the[ Meta for Developers.](https://developers.facebook.com/apps)​
* Choose your App and Open it. You need to have the **Developer** Role.
* Open **Settings** > **Basic** in the navigation.
* Scroll down you find the **Install** **Referrer Decryption Key** at the bottom of the page.

![Facebook Install Referrer Decryption Key](<../.gitbook/assets/248890969\_2987092494847431\_4032109750337904341\_n (1).png>)

## Creative Management

Transmitting creatives to facebook is done in multiple use cases:

1. Transmitting creative sets to existing or new ad sets
2. Testing creatives using justtrack's creative test feature (IPM, CTR)

### Supported Creative-Sets

* Image (1) + Headline (1-5) + Primary Text (1-5)
* Video (1) + Headline (1-5) + Primary Text (1-5)
* Video (1) + Playable (1) + Headline (1-5) + Primary Text (1-5)

### Prerequisites

#### 1. Create an app

Go to [the Facebook developer site](https://developers.facebook.com/apps/) and create an app for your business account.

1. Type = Business
2. Display name = Justtrack
3. App contact email = `your email`
4. Business Account = select your business account

#### 2. Add Marketing API to your App

* add the `Marketing API`
* click on `Set up`

#### 3. Generate token

1. Go to the Facebook Business settings
2. Go to `system users`
3. Create a system user if there is none (type `employee`)
4. Add all assets to the system user you want justtrack to be able to manage. E.g. If you want to create ads for a specific app, the system user needs permissions to read the app.
5. Click `Generate token`
6. Select the just created app `justTrack`
7. Select the permissions [`ads_read`](https://developers.facebook.com/docs/permissions/reference/ads\_read),[`read_insights`](https://developers.facebook.com/docs/permissions/reference/read\_insights) (spend-import) and [`ads_management`](https://developers.facebook.com/docs/permissions/reference/ads\_management) (creating ads and adcreatives)
8. Create the token
9. Add this token to the justtrack dashboard: admin -> networks -> your facebook network(edit) -> credentials -> token

### Needed data

![Data structure](<../.gitbook/assets/fbpublish.drawio (1).png>)

1. You need an app which you want to promote. Create a `product` and a client for `ios` and/or `android`.
2. The client, you want to promote, needs the `network attributes` Facebook `App URL` and Facebook`Page ID`. Add them in the dashboard.
3. If you publish a creative-set to Facebook, justtrack will create an ad with the name of the creative-set. Justtrack needs to know for which adSet it should create an ad. Add the [Facebook ad set id](https://www.facebook.com/business/help/2534657046763437) to the `externalId` of the ad Set in our dashboard.
4. Add the [Facebook Business id ](https://www.facebook.com/business/help/1181250022022158?id=180505742745347)to the Campaign Attribute `act`
