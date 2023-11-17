# Client Network Vendor Attributes

### List networks

```
List the vendor attributes for client Networks.
```

> ```bash
> curl --location -X POST 'management/v0/client-network-vendor-attributes' \
> -H 'X-API-KEY: <API KEY>'
> ```

### Request

The message body for `/client-network-vendor-attribute` is a `filter` object:

```json
{
   "filter": {
        "matches": [
            {
                "dimension": "network.vendor",
                "operator": "~",
                "values": [
                    "unity"
                ]
            }
        ]
    }
}
```

You can filter on the following dimensions:

| Dimension                           | Description               |
| ----------------------------------- | ------------------------- |
| `network.vendor`                    | The name of the Network   |
| `clientNetworkVendorAttribute.name` | The name of the attribute |

If you don't want to filter the list, you can use an empty object in the request body:

```json
{}
```

### Response

```json
{
    "total": 2,
    "results": [
        {
            "id": 1,
            "name": "campaignSetId",
            "vendor": "unity",
            "createdAt": "2021-07-15T12:33:58Z",
            "updatedAt": "2021-07-15T12:33:58Z"
        },
        {
            "id": 2,
            "name": "clientCustomerId",
            "vendor": "adwords",
            "createdAt": "2021-07-29T10:14:24Z",
            "updatedAt": "2021-07-29T10:14:24Z"
        }
    ]
}
```

| Name    | Type             | Description                                                                                      |
| ------- | ---------------- | ------------------------------------------------------------------------------------------------ |
| total   | int              | The total number of attributes based on the filter.                                              |
| results | array of objects | An array containing attribute details, including the attribute's id, name, and Network (vendor). |
