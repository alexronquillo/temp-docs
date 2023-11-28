# Campaign

## List campaign

<pre><code><strong>This API provides the data of created campaigns for the current user's business unit
</strong></code></pre>

> ```
> curl -X POST -H X-API-Key: <API_KEY> -d '{"page": {"offset":0, "limit": 100}, "filter":{"networkVendor":"<vendor name>", "externalCampaignId": "<external campaign id>"}}'
> https://api.justtrack.io/management/v0/campaigns
> ```

### Request

```json
{
    "page": {
        "offset": 0,
        "limit": 100
    },
    "filter": {
        "networkVendor": "<networkVendor>",
        "externalCampaignId": "<external campaign id>"
    }
}
```

| Name               | Type   | Description                                                                                |
| ------------------ | ------ | ------------------------------------------------------------------------------------------ |
| offset             | int    | `offset` clause skips the `offset` rows before beginning to return the response. Default 0 |
| limit              | int    | `limit` determines the number of campaigns returned in the response. Default 100           |
| networkVendor      | string | networkVendor determines the supported network vendor. Not required                        |
| externalCampaignId | string | externalCampaignId determines the network-specific campaignId. Not required                |

### Response

```json
{
  "result": [
    {
      "id": int,
      "campaignTypeId": int,
      "goalId": int,
      "name": "string",
      "networkId": int,
      "optimizationType": "string",
      "clientId": int,
      "createdAt": "string",
      "updatedAt": "string",
      "attributes": [
        {
            "name": "fb_adgroup_id",
            "value": "string"
        },
        {
            "name": "fb_adset_id",
            "value": "string"
        },
        {
            "name": "fb_campaign_id",
            "value": "string"
        },
        {
            "name": "act",
            "value": "string"
        }
      ]
    }
  ]
}
```

## Create campaign

<pre class="language-markdown"><code class="lang-markdown"><strong>This API allows you to create a campaign. 
</strong></code></pre>

> ```bash
> curl -X POST -H X-API-Key: <API_KEY> 
> https://api.justtrack.io/management/v0/campaign
> ```

### Request

The general request to the Create Campaign API looks like:

<pre class="language-json"><code class="lang-json"><strong>{
</strong><strong>    "optimizationType": "string",
</strong>    "campaignTypeId": int,
    "clientId": int,
    "networkId": int,
    "countries": ["string", "string"],
    "name": "string",
    "attributes": [
        {
            "name": "string",
            "value": "string"
        },
        ...
    ]
}
</code></pre>

<table><thead><tr><th width="249.33333333333331">Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>optimizationType</td><td>string</td><td>Available options are "cpa" or "cpi".</td></tr><tr><td>campaignTypeId</td><td>int</td><td><p>Available options are:</p><ul><li>1 for acquision</li><li>2 for retargeting</li></ul></td></tr><tr><td>clientId</td><td>int</td><td>The Id of the client. You can obtain it by using the <a href="app.md">app API</a>.</td></tr><tr><td>networkId</td><td>int</td><td>The Id of the network. You can obtain it by using the <a href="network.md">network API.</a></td></tr><tr><td>countries</td><td>[]string</td><td>The list of the countries in ISO2 format. For example ["DE", "EN"].</td></tr><tr><td>name</td><td>string</td><td>The name of the new campaign.</td></tr><tr><td>attributes</td><td><a href="campaign.md#attributes">Attributes</a> list</td><td>The attributes are network-specific data to link JustTrack with the Ad Network.</td></tr><tr><td></td><td></td><td></td></tr></tbody></table>

### Attributes

| Name  | Type   | Description                                      |
| ----- | ------ | ------------------------------------------------ |
| name  | string | The attribute name specific for the Ad Network.  |
| value | string | The attribute value specific for the Ad Network. |

### Attributes Facebook example

```json
"attributes": [
        {
            "name": "fb_adgroup_id",
            "value": "string"
        },
        {
            "name": "fb_adset_id",
            "value": "string"
        },
        {
            "name": "fb_campaign_id",
            "value": "string"
        },
        {
            "name": "act",
            "value": "string"
        }
    ]
```

### Response

```json
{
  "id": int,
  "active": boolean
}
```

##
