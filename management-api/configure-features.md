# Configure Features

You configure features by app and network. If you want to configure features for multiple apps, you must call this endpoint for each app.

{% hint style="info" %}
For each feature, you must create all the required keys, which are specified by the [Vendor Configuration](vendor-configuration.md) API.
{% endhint %}

The available features are:

* `attribution`
* `postback`

You can switch between these features by exchanging the placeholder in the URL path to the desired feature:

```
https://api.justtrack.io/management/v0/configuration/:feature
```

{% hint style="info" %}
For attribution viewEventTimeFrame and clickEventTimeFrame, use [ISO8601 duration-only ](https://en.m.wikipedia.org/wiki/ISO\_8601#Time\_intervals)format, i.e. P1DT0H0M
{% endhint %}

## List configurations

List configurations returns the list of feature configurations for the given app and network.

```bash
curl --location -X POST 'https://api.justtrack.io/management/v0/configuration/attribution' \
-H 'X-API-KEY: <API KEY>'
```

### Request

The message body is an object:

```json
{
    "appId": int,
    "networkId": int
}
```

<table><thead><tr><th width="193">Parameter</th><th width="80.33333333333331">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>networkId</code></td><td>int</td><td>justtrack internal id of the network. You can find it with the <a href="network.md#list-networks">network list API</a>.</td></tr><tr><td>appId</td><td>int</td><td>justtrack internal id of the app. You can find it with the <a href="app.md">app list API</a>, or use the return value from <a href="app.md#create-app">app create API</a>.</td></tr></tbody></table>

### Response

```json
[
  {
    "id": int,
    "app": {
      "id": int
    },
    "network": {
      "id": int,
      "vendor": string
    },
    "key": string,
    "value": string,
    "sensitive": boolean
  }
]
```



| Field          | Type    | Description                                        |
| -------------- | ------- | -------------------------------------------------- |
| id             | int     | Id of the config value                             |
| app.id         | int     | justtrack internal app id                          |
| network.id     | int     | justtrack internal network id                      |
| network.vendor | string  | Name of the network vendor                         |
| key            | string  | Name of the vendor configuration key               |
| value          | string  | Value of the vendor configuration                  |
| sensitive      | boolean | True if the value is confidential. False otherwise |

## Update configurations

Update configurations creates or updates feature-specific configurations for a given app and network.

```bash
curl --location -X PUT 'https://api.justtrack.io/management/v0/configuration/attribution' \
-H 'X-API-KEY: <API KEY>'
```

{% hint style="info" %}
You must provide values for all keys listed by [List configurations](configure-features.md#list-configurations). Otherwise, the feature will not work as expected.
{% endhint %}

### Request

The message body is an object:

```json
{
    "appId": int,
    "networkId": int,
    "configuration": [
        {
            "key": string,
            "value": string
        }
    ]
}
```

| Parameter           | Type   | Description                                                                                              |
| ------------------- | ------ | -------------------------------------------------------------------------------------------------------- |
| appId               | int    | justtrack internal app id                                                                                |
| networkId           | int    | justtrack internal app id                                                                                |
| configuration.key   | string | Name of the configuration. Has to be one which is returned by the list call for this appId and networkId |
| configuration.value | string | Value of the configuration                                                                               |

### Response

```
[
  {
    "id": int,
    "app": {
      "id": int
    },
    "network": {
      "id": int,
      "vendor": string
    },
    "key": string,
    "value": string,
    "sensitive": boolean
  }
]
```

| Field          | Type    | Description                                         |
| -------------- | ------- | --------------------------------------------------- |
| id             | int     | Id of the config value                              |
| app.id         | int     | justtrack internal app id                           |
| network.id     | int     | justtrack internal network id                       |
| network.vendor | string  | Name of the network vendor                          |
| key            | string  | Name of the vendor configuration key                |
| value          | string  | Value of the vendor configuration                   |
| sensitive      | boolean | True, if the value is confidential. False otherwise |
