# UserEvent API

When you build a `UserEvent`, you can either:

* Provide values to the constructor.
* Initialize an empty event and later call setters for other properties.

### UserEvent Constructors

`UserEvent` has the following constructors:

```java
public class UserEvent {
    public UserEvent(string pName)
    public UserEvent(string pName, double pValue, Unit pUnit)
    public UserEvent(string pName, Money pMoney)
}
```

The only requirement for a new event is a name (`pName`). Once you've assigned an event name, it can later no longer be changed.

The `value` and `unit` can only be provided together and default to `0.0` and no unit if not provided. Alternatively, an event can carry a monetary value instead of a value with a unit.

### UserEvent setters

You can also set properties and dimensions after initialization, using the following methods:

```java
public UserEvent AddDimension(string pDimension, string pValue)
public UserEvent AddDimension(Dimension pDimension, string pValue)
public UserEvent RemoveDimension(string pDimension)
public UserEvent RemoveDimension(Dimension pDimension)
public UserEvent SetValue(double pValue, Unit pUnit)
public UserEvent SetValue(Money pMoney)

// convenience wrappers for .set()
public UserEvent SetCount(double pCount)
public UserEvent SetSeconds(double pSeconds)
public UserEvent SetMilliseconds(double pMilliseconds)
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
