# Bid Upload

## Upload Bids

With this API you can upload a batch of bids, similar to the [CSV upload](broken-reference). The same hierarchy, rules, and limitations apply.

```bash
curl -X POST -H 'X-API-KEY: {api key}' 'https://api.justtrack.io/management/v0/bids/upload' \
-d '[{"campaign": {"id": 1234}, "country": "DE", "optimalBidUsd": 0.01, "delete": false}]'
```

{% hint style="info" %}
This API doesn't check for duplicate bids. justtrack will apply each uploaded bid one after the other.
{% endhint %}

### Request

```json
[
    {
        "adSetId": integer,
        "campaign": {
            "id": integer
        },
        "country": string,
        "sourceId": string,
        "optimalBidUsd": float,
        "delete": boolean
    }
]
```



| Name          | Type    | Description                                                                                                               |
| ------------- | ------- | ------------------------------------------------------------------------------------------------------------------------- |
| adSetId       | int     | <p>justtrack internal ad set id<br>Optional: set to <em>null</em> when not needed</p>                                     |
| campaign.id   | int     | justtrack internal campaign id                                                                                            |
| country       | string  | ISO 3166-1 alpha-2 code of your country, e.g. "DE"                                                                        |
| sourceId      | string  | <p>Identifier provided by ad network to target specific source app.<br>Optional: set to <em>null</em> when not needed</p> |
| optimalBidUsd | float   | The target bid value, in USD                                                                                              |
| delete        | boolean | <p>Whether this operation is <em>delete</em> or not<br>Optional: default is <em>false</em></p>                            |

### Response

#### Success: HTTP 204

```json
{}
```

#### Invalid Request: HTTP 400

```json
{
    "error": string
    "bidsValidation": [
        {
            "adSetId": integer
            "campaign": {
                "id": integer,
                "name": string
            },
            "country": {
                "id": integer,
                "name": string,
                "iso2": string
            },
            "delta": {
                "changePercentage": float,
                "newValue": float,
                "oldValue": float
            },
            "network": {
                "id": integer,
                "name": string
            },
            "sourceId": string,
            "status": string,
            "message": string
        }
    ]
}
```

For each bid failing validation an entry to _bidsValidation_ is added, detailing its dimensions, the value change and the reason why it was rejected. Possible reasons include:

* ad set bidding is not enabled for this network
* ad set not found
* bidding is not enabled for this network
* campaign bidding is not enabled for this network
* countries of the campaign does not contain the bid's specified country
* campaign has wrong optimization type for bidding
* missing credentials
* missing campaign attributes
* missing client network vendor attributes
* missing network vendor attributes
* source id bidding is not enabled
* source id bid requires ad set to be set
* can not delete campaign bid
* can not delete non-existent bid
* bid value is below minimum
* given decimal precision is not supported for this network

#### Error: HTTP 500

```json
{
    "err": string
}
```
