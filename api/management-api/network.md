# Network

### List networks

```
List networks return the list of networks for the current user's business unit.
```

> ```bash
> curl --location -X POST 'https://api.justtrack.io/management/v0/networks' \
> -H 'X-API-KEY: <API KEY>'
> ```

### Request

The message body for is a `filter` object:

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

| Dimension        | Description             |
| ---------------- | ----------------------- |
| `network.vendor` | The name of the Network |

If you don't want to filter the list, you can use an empty object in the request body:

```json
{}
```

### Response

```json
{
  "result": [
    {
      "id": int,
      "name": "string",
      "vendor": "string",
      "spendCurrency": "string",
      "createdAt": "string",
      "updatedAt": "string"
    }
  ]
}
```

| Name          | Type   | Description                      |
| ------------- | ------ | -------------------------------- |
| id            | int    | Id of the network                |
| name          | string | Name of the network              |
| vendor        | string | Name of the vendor               |
| spendCurrency | string | Spend currency                   |
| createdAt     | string | The date of network creation.    |
| updatedAt     | string | The date of last network update. |
