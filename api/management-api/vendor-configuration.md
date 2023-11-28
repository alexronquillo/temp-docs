# Vendor Configuration

Vendor configurations specify keys which are required for certain justtrack features. Without them, justtrack won't be able to successfully operate or integrate with partners.

{% hint style="info" %}
A configuration key may appear for different features. You have to fill it every time.&#x20;
{% endhint %}

## List vendor configurations

List vendor configurations returns the list of vendor configurations for a requested feature.

```bash
curl --location -X POST 'https://api.justtrack.io/management/v0/vendor-configurations' \
-H 'X-API-KEY: <API KEY>'
```

### Request

The message body for is a `filter` object:

```json
{
   "filter": {
        "matches": [
            {
                "dimension": "vendorConfiguration.feature",
                "operator": "=",
                "values": [
                    "attribution"
                ]
            },
            {
                "dimension": "vendorConfiguration.vendor",
                "operator": "=",
                "values": [
                    "unity"
                ]
            }
        ],
        "bool": "AND"
    }
}
```

You can filter on the following dimensions:

| Dimension                   | Description             |
| --------------------------- | ----------------------- |
| vendorConfiguration.vendor  | The name of the vendor  |
| vendorConfiguration.feature | The name of the feature |

Currently available features are:

* attribution
* postback

### Response

```json
[
    {
        "key": string,
        "sensitive": bool
    }
]
```



| Name      | Type    | Description                                       |
| --------- | ------- | ------------------------------------------------- |
| key       | string  | The name of the key                               |
| sensitive | boolean | True, if the key is confidential. False otherwise |
