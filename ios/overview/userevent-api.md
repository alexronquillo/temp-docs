# UserEvent API

When you build a `UserEvent`, you can either:&#x20;

* Provide values to the constructor.
* Initialize an empty event and later call setters for other properties.&#x20;

### UserEvent Constructors

`UserEvent` has the following constructors:

```java
public class UserEvent {
    public init(_ name: String)
    public init(name: String, value: Double, unit: Unit)
    public init(name: String, money: Money)
}
```

The only requirement for a new event is a `name`. Once you've assigned an event name, it can later no longer be changed.

The `value` and `unit` can only be provided together and default to `0.0` and no unit if not provided. Alternatively, an event can carry a monetary value instead of a value with a unit.

### UserEvent setters

You can also set properties and dimensions after initialization, using the following methods:

```java
public func add(dimension: String, value: String) -> UserEvent
public func add(dimension: Dimension, value: String) -> UserEvent
public func remove(dimension: String) -> UserEvent
public func remove(dimension: Dimension) -> UserEvent
public func set(value: Double, unit: Unit) -> UserEvent
public func set(money: Money) -> UserEvent

// convenience wrappers for .set()
public func set(count: Double) -> UserEvent
public func set(seconds: Double) -> UserEvent
public func set(milliseconds: Double) -> UserEvent
```

### UserEvent restrictions

When you create a custom event, you must adhere to the following requirements:

* The event name:&#x20;
  * Cannot be empty.
  * Must be shorter than 256 characters.
  * Is case-sensitive.
  * Can only consist of printable ISO 8859-1 characters (U+0020 to U+007E as well as U+00A0 to U+00FF).
* Dimension names:&#x20;
  * Must be shorter than 256 characters.
  * Can only consist of printable ISO 8859-1 characters (U+0020 to U+007E as well as U+00A0 to U+00FF).
  * Are case-sensitive.
* Dimension values:&#x20;
  * Must be shorter than 4096 characters
  * Can only consist of printable ISO 8859-1 characters (U+0020 to U+007E as well as U+00A0 to U+00FF).
* The event can have a maximum of 10 total dimensions.
* The value of a user event must be finite (i.e., not NaN or ±Infinity).&#x20;
* If you provide a monetary value, the currency needs to be a 3 letter uppercase ISO 4217 string.
