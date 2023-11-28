# App

## List apps

```
List app return the list of apps for the current user's business unit.
```

> ```bash
> curl --location -X POST 'https://api.justtrack.io/management/v0/apps' \
> -H 'X-API-KEY: <API KEY>'
> ```

### Response

```
{
  "result": [
    {
      "id": int,
      "platformId": int,
      "packageId": string,
      "storeId": string,
      "name": "string",
      "createdAt": "string",
      "updatedAt": "string"
    }
  ]
}
```

| Name       | Type   | Description                                                                                                                                   |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| id         | int    | Id of the product                                                                                                                             |
| platformId | int    | <p>The App's platform; one of:</p><ul><li><code>1</code> for android </li><li><code>2</code> for ios</li><li><code>3</code> for web</li></ul> |
| packageId  | string | Application package id                                                                                                                        |
| storeId    | string | Application store id as used by the Apple or Google App Store                                                                                 |
| name       | string | Name of the product                                                                                                                           |
| createdAt  | string | The date of product creation                                                                                                                  |
| updatedAt  | string | The date of the latest product update                                                                                                         |

## Create App

```
With this API, you can create an App. 
```

> ```http
> curl -X POST -H X-API-Key: <API_KEY> 
> https://api.justtrack.io/management/v0/app
> ```

### Request

The general request to the Create App API looks like:

```json
{
    "name": "test 123",
    "platformId": 1,
    "storeId": "gg.sunday.cate",
    "iconLink": "https://play-lh.googleusercontent.com/If5wCREVhk1ibdZd8g67oShl_Vnm0qyx3OayiBl7Sm3UGr_74_0ZrWEmLXo5XesrGw=w480-h960",
    "packageId": "packageid",
    "networkAttributes": [
        {
            "attribute": {
                "id": 1
            },
            "value": "456"
        }, {
            "attribute": {
                "id": 2
            },
            "value": "789"
        }
    ]
}
```

#### General parameters

| Name       | Type   | Description                                                                                                                                   |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| name       | string | The name of the App to create                                                                                                                 |
| platformId | int    | <p>The App's platform; one of:</p><ul><li><code>1</code> for android </li><li><code>2</code> for ios</li><li><code>3</code> for web</li></ul> |
| storeId    | string | Unique Id of the application in the store                                                                                                     |
| iconLink   | string | Icon URL taken from store                                                                                                                     |
| packageId  | int    | Id of package                                                                                                                                 |

{% hint style="info" %}
We validate the following constraints when creating an app:

* the package id must be used only by you as a customer
* the tuple (package id, platform id) must be unique
* the tuple (name, platform id) must be unique
* the store id must only be used once
{% endhint %}

### Response

#### General fields

```json
{
    "id": 123,
    "name": "test 123",
    "platformId": 1,
    "apiToken": "abcd1234",
    "networkAttributes": [
        {
            "id": 1,
            "attribute": {
                "id": 1,
                "name": "clientCustomerId",
                "vendor": "adwords",
                "createdAt": "2021-07-29T10:14:24Z",
                "updatedAt": "2021-07-29T10:14:24Z"
            },
            "value": "456",
            "createdAt": "2023-08-08T09:54:54Z",
            "updatedAt": "2023-08-08T09:54:54Z"
        },
        {
            "id": 2,
            "attribute": {
                "id": 2,
                "name": "firebaseAppId",
                "vendor": "adwords",
                "createdAt": "2022-05-23T11:45:19Z",
                "updatedAt": "2022-05-23T11:45:19Z"
            },
            "value": "789",
            "createdAt": "2023-08-08T09:54:53Z",
            "updatedAt": "2023-08-08T09:54:53Z"
        }
    ]
}
```

| Name                                                               | Type             | Description                                                                                                                                                                                                                      |
| ------------------------------------------------------------------ | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Id                                                                 | string           | Unique Id of the App in justtrack                                                                                                                                                                                                |
| name                                                               | string           | The name of the App to create                                                                                                                                                                                                    |
| platformId                                                         | int              | <p>The App's platform; one of:</p><ul><li><code>1</code> for Android </li><li><code>2</code> for iOS</li><li><code>3</code> for Web</li></ul>                                                                                    |
| apiToken                                                           | string           | The API token for the Network.                                                                                                                                                                                                   |
| <p><del>networkAttributes</del><br><strong>deprecated</strong></p> | array of objects | <p>For some Networks, you need to configure attributes when creating the App. This object shows the attributes you created.<br><br>Refer to <a href="app.md#networkattributes-1">networkAttributes</a> for more information.</p> |
|                                                                    |                  |                                                                                                                                                                                                                                  |
|                                                                    |                  |                                                                                                                                                                                                                                  |
|                                                                    |                  |                                                                                                                                                                                                                                  |

#### networkAttributes

`networkAttributes` is an array of objects. Each object looks like this:

```json
{
    "id": 1,
    "attribute": {
        "id": 1,
        "name": "clientCustomerId",
        "vendor": "adwords",
        "createdAt": "2021-07-29T10:14:24Z",
        "updatedAt": "2021-07-29T10:14:24Z"
    },
    "value": "456",
    "createdAt": "2023-08-08T09:54:54Z",
    "updatedAt": "2023-08-08T09:54:54Z"
}
```

| Name      | Type   | Description                                                                                                                 |
| --------- | ------ | --------------------------------------------------------------------------------------------------------------------------- |
| id        | int    | The Network attribute Id.                                                                                                   |
| attribute | object | Holds details about the attribute, including the attribute name and the Network (vendor) to which to the attribute belongs. |
| value     | string | The value of the attribute                                                                                                  |
| createdAt | string | The date and time the Feature was created in the ISO 8601 format. The timezone is UTC.                                      |
| updatedAt | string | The date and time the Feature was last updated in the ISO 8601 format. The timezone is UTC.                                 |
