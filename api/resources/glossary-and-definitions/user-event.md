# User Event

User events record in-app user behaviors. With these you can analyze how your users are using your app. User events are one of the primary data points that power dashboards, tables, and charts in justtrack. You'll find user event data in many views including:

* [Basic Funnel](https://dashboard.justtrack.io/app-analytics/basic)
* [Monetization](https://dashboard.justtrack.io/app-analytics/monetization)
* [Event Drill Down](https://dashboard.justtrack.io/app-analytics/event-drill-down)

## Event structure

A user event is made up of three components:

1. (Required) An event name
2. (Optional) Up to 10 dimensions
3. (Optional) A value

### Dimensions

User events can have **dimensions** that store information about the event. For example, if you are tracking a level completion event, you might store the completed level as a dimension on that event.

Dimensions store limited, discrete values. For example, a level name, a button name, or a login provider. They have the following restrictions:

* A single event can store a maximum of 10 dimensions.
* You can only send 1000 distinct values per dimension per day.

{% hint style="info" %}
Many predefined events include common dimensions by default, you can read more about those in our [Predefined Events documentation](http://127.0.0.1:5000/s/CSwomFswqKEitapGh0xs/readme/predefined-events).
{% endhint %}

### Value

Along with its dimensions, a user event can also have a single **value**. This value is different from the event's dimensions in both its purpose and the method by which it is stored. One example of a value is: if you are tracking a level completion event, you might store the duration of time it takes an interstitial ad to load.

A value may be a decimal number in a continuous range of possibilities and is paired with either a unit or a currency. For example, an amount of money spent in a specified currency or a duration of time with a specified time precision.

The possible value units are:

| Unit        | Description                             |
| ----------- | --------------------------------------- |
| count       | The number of times something happened. |
| second      | A duration measured in seconds.         |
| millisecond | A duration measured in milliseconds.    |

Otherwise, if you're storing a monetary value, you need to specify the currency.

{% hint style="info" %}
Some predefined events specify a common value for you to send with it, you can read more about those in our [Predefined Events documentation](http://127.0.0.1:5000/s/CSwomFswqKEitapGh0xs/readme/predefined-events).
{% endhint %}

## Predefined User Events

Some user event types are defined by justtrack. These are events that are common in many applications, such as a user:

* Opens the app
* Starts a level
* Confirms a purchase

Because we predefine these events, some metrics are calculated for you if you send data in certain predefined events. For example, if you send level start, fail, and finish events, we can automatically populate game progression funnel data without any extra configuration.

Many predefined events include default dimensions and values. However, you can also add your own dimensions.

{% hint style="info" %}
Read more about our predefined events [here](http://127.0.0.1:5000/s/CSwomFswqKEitapGh0xs/readme/predefined-events).
{% endhint %}

## Custom User Events

Along with predefined events, you can also send custom events to your justtrack account. You define these events yourself and they are not given any special attention in the platform.

For custom events, you must specify all dimensions and a value if you want to use them.
