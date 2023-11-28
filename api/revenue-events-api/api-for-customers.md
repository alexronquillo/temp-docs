# Customers

## Revenue Events

Justtrack offers a S2S solution to receive your revenue events in real-time.

#### **API** <a href="#api" id="api"></a>

URL: https://sink.justtrack.io/monetization/v0/jt

#### **Required Parameters** <a href="#required-parameters" id="required-parameters"></a>

The following path parameters are required in the URL path so revenue events are getting tracked.

| Parameter     | Description                                                                                   |
| ------------- | --------------------------------------------------------------------------------------------- |
| apikey        | Your justtrack API key                                                                        |
| platform      | **ios** or **android**                                                                        |
| packageId     | The Package ID / Bundle ID of the app                                                         |
| transactionid | Unique transaction ID that can be used to trace and deduplicate events                        |
| userid        | Either the justtrack user id or your custom user id, which you provided via the justtrack SDK |
| value         | Revenue value in USD                                                                          |

#### Optional Parameters <a href="#optional-parameter" id="optional-parameter"></a>

| Provider                 | Short Handle                                                         |
| ------------------------ | -------------------------------------------------------------------- |
| monetizationnetwork      | Network that filled the ad impression                                |
| monetizationprovider     | Reporting Provider                                                   |
| monetizationbundleid     | App bundle ID/package name of the advertised app                     |
| monetizationinstancename | Identify which position in the waterfall received the ad impression  |
| monetizationplacement    | Name of placement within the app                                     |
| monetizationsegment      | Identifier in case ads are limited to specific audience groups       |
| monetizationtestgroup    | Identifier in case users are split into different groups for testing |
| monetizationtype         | Type of shown ad                                                     |
| happenedat               | The time when the event happened in ISO 8601 format                  |

#### Example Request <a href="#example-get-request" id="example-get-request"></a>

ttps://sink.justtrack.io/monetization/v0/jt?apikey=123\&platform=android\&packageid=com.my.app\&transactionid=transaction-id-123\&userid=custom-user-id-123\&monetizationnetwork=network\&monetizationprovider=provider\&value=1.98

### Best Practices

We highly recommend to provide at least monetizationnetwork and monetizationprovider as this significantly increases your possibilities drill into you user's behaviour.
