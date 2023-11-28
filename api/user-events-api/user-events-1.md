# User Events

### **API**

Request Method: GET

URL: https://sink.justtrack.io/userevents/v0

### **Required Parameters**

The following parameters are required so events are getting tracked.

<table><thead><tr><th width="243">Parameter</th><th>Description</th><th data-hidden data-type="files"></th></tr></thead><tbody><tr><td>apiKey</td><td>Your justtrack API key</td><td></td></tr><tr><td>userId</td><td>Either the justtrack user id or your custom user id, which you provided via the justtrack SDK</td><td></td></tr><tr><td>platform</td><td><strong>ios</strong> or <strong>android</strong></td><td></td></tr><tr><td>packageId</td><td>The Package ID / Bundle ID of the app</td><td></td></tr><tr><td>eventName</td><td>A custom name for the event</td><td></td></tr></tbody></table>

### Optional Parameter

The following parameter is optional and used in case events cannot be sent in real time. If no timestamp is provided, we will use the current time.

<table><thead><tr><th width="243">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>timestamp</td><td>The time when the event happened in ISO 8601 format</td></tr></tbody></table>

### Example GET Request

{% code overflow="wrap" %}
```
https://sink.justtrack.io/userevents/v0?userId=f1004a2c-b04d-4e71-bee1-5b99ca404951&platform=android&packageId=app.package.id&eventName=event_name&timestamp=2022-05-12T09:35:35Z&apiKey=bec4afed-bfdc-4434-8909-ee7666b01d7b
```
{% endcode %}
