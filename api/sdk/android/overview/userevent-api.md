# UserEvent API

When you build a `UserEvent`, you can either:&#x20;

* Provide values to the constructor.
* Initialize an empty event and later call setters for other properties.&#x20;

### UserEvent Constructors

`UserEvent` has the following constructors:

```java
class UserEvent {
    public UserEvent(@NonNull String name)
    public UserEvent(@NonNull String name, double value, @NonNull Unit unit)
    public UserEvent(@NonNull String name, @NonNull Money money)
}
```

The only requirement for a new event is a `name`. Once you've assigned an event name, it can later no longer be changed.

The `value` and `unit` can only be provided together and default to `0` and no unit if not provided. Alternatively, an event can carry a monetary value instead of a value with a unit.

### UserEvent setters

You can also set properties and dimensions after initialization, using the following methods:

```java
public UserEvent addDimension(String, String);
public UserEvent addDimension(Dimension, String);
public UserEvent removeDimension(String);
public UserEvent removeDimension(Dimension);
public UserEvent setValue(double, Unit);
public UserEvent setValue(Money);

// convenience wrappers for .setValue()
public UserEvent setCount(double);
public UserEvent setSeconds(double);
public UserEvent setMilliseconds(double);
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
  * May only consist of:
    * lowercase letters in the latin alphabet (U+0061 to U+007A)
    * underscores (U+005F)
    * numbers (U+0030 to U+0039)
* Dimension values:&#x20;
  * Must be shorter than 4096 characters
  * Can only consist of printable ISO 8859-1 characters (U+0020 to U+007E as well as U+00A0 to U+00FF).
* The event can have a maximum of 10 total dimensions.
* The value of a user event must be finite (i.e., not NaN or ±Infinity).&#x20;
* If you provide a monetary value, the currency needs to be a 3 letter uppercase ISO 4217 string.

{% hint style="danger" %}
If your event does not match the following criteria, it will not be recorded in the justtrack platform.
{% endhint %}
