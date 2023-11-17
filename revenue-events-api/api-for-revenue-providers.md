# Revenue Providers

## Revenue Events

For many revenue providers justtrack offers a S2S solution to receive revenue postbacks in real-time.

#### **API** <a href="#api" id="api"></a>

URL: https://sink.justtrack.io/monetization/v0/{provider}/{platform}/{packageId}

#### **Required Path Parameters** <a href="#required-parameters" id="required-parameters"></a>

The following path parameters are required in the URL path so revenue events are getting tracked.

| Parameter | Description                           |
| --------- | ------------------------------------- |
| provider  | Short handle of the provider name     |
| platform  | **ios** or **android**                |
| packageId | The Package ID / Bundle ID of the app |

#### Provider Short Handles <a href="#optional-parameter" id="optional-parameter"></a>

| Provider         | Short Handle    |
| ---------------- | --------------- |
| AdColony         | adcolony        |
| Adgem            | adgem           |
| Applovin         | applovin        |
| Bitlabs          | bitlabs         |
| Cint             | cint            |
| CPX Research     | cpxresearch     |
| Dalia            | dalia           |
| Fyber            | fyber           |
| InBrain          | inbrain         |
| OfferToro        | offertoro       |
| Pollfish         | pollfish        |
| Revenue Universe | revenueuniverse |
| TapResearch      | tapresearch     |
| TheoremReach     | theoremreach    |

#### Example Request <a href="#example-get-request" id="example-get-request"></a>

https://sink.justtrack.io/monetization/v0/fyber/android/app.package.id

### Revenue Event Forwarding

After receiving and processing the revenue events, justtrack can forward the events to an API of your choice. Thus, for every provider and app a "Forward URL" can be configured via the justtrack dashboard. We will forward the revenue postback as we received it and only replace domain and path.
