# Send user events

With the justtrack SDK, you can monitor and record user behaviors as events. These allow you to track how your users are using your app. For each event, you can also specify dimensions which you can later use to filter, sort, and group your events in the dashboard.

In this guide, you'll learn to:&#x20;

* Send predefined events
* Send custom events
* Await the results of publishing events

## Publish a predefined user event

With our SDK, you can send predefined events to your justtrack account. These events are defined by justtrack and are given special attention in the platform. For example, some metrics are calculated for you if you send data in certain predefined events.

{% hint style="info" %}
You can find our list of predefined events [here](../readme/predefined-events.md).
{% endhint %}

To send a predefined event, you first create an event object:

```swift
let event = JtLevelStartEvent(jtLevelName: "LEVEL_1")
```

Here, `JtLevelStartEvent` is a subclass of `UserEvent`. It represents a [JtLevelStart](../readme/predefined-events.md#jtlevelstart) and accepts a single predefined dimension, called "jt\_level\_name". In this example, you pass the value for that dimension in the constructor.

You can add more dimensions with `.add()`:

```swift
let event = JtLevelStartEvent(jtLevelName: "LEVEL_1")
    .add(dimension: "dimension_name", value: "value")
```

{% hint style="info" %}
You can pass all predefined dimensions that belong to a predefined event to the constructor. For all other dimensions, you must use `.add()`.
{% endhint %}

When you've created and configured an event object, call `.publish()`:

```swift
sdk.publish(event: event)
```

This sends the event to the justtrack platform where you can visualize and analyze your data.

## Publish a custom user event

Along with predefined events, you can also send custom events to your justtrack account. You define these events yourself and they are not given any special attention in the platform.

To send a custom event, you first create an event object:

```swift
let event = UserEvent("my_event")
```

Here, you create a custom `UserEvent` object and supply an event name, "my\_event".&#x20;

You can add dimensions to your custom event with `.add()`:

```swift
let event = UserEvent("my_event")
    .add(dimension: "dimension_name", value: "value")
```

When you've created and configured an event object, call `.publish()`:

```swift
sdk.publish(event: event)
```

This sends the event to the justtrack platform where you can visualize and analyze your data.

## Conclusion

Now that you know how to send events to your justtrack account, you can review further details of the `UserEvent` class in our [UserEvent API documentation](overview/userevent-api.md).
