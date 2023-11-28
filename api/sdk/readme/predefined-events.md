# Predefined Events

The SDK provides a list of predefined events as static fields of the `UserEvent` class. Below you can find a list of these events with their description and what dimensions are expected to be provided with them.

## JtAdClick

You can use this event to capture details of an event in which an advertisement is clicked.

### Default dimensions

| Name              | Description                                                | Suggested values               |
| ----------------- | ---------------------------------------------------------- | ------------------------------ |
| jt\_ad\_unit      | To specify the type of advertisement.                      | banner, interstitial, rewarded |
| jt\_ad\_sdk\_name | The SDK which served the advertisement.                    | Ironsource, Adjoe, Vungle      |
| jt\_ad\_network   | The ad network which served the advertisement.             | Ironsource, Adjoe, Vungle      |
| jt\_ad\_placement | Information related to the placement of the advertisement. | Level End, Game Finish, Shop   |

### Extra properties

| Parameter name | Description            | Suggested values |
| -------------- | ---------------------- | ---------------- |
| count          | The count of the event | 12345            |

## JtAdClose

You can use this event to capture details of an event in which an advertisement is closed.

### Default dimensions

| Name              | Description                                                | Suggested values               |
| ----------------- | ---------------------------------------------------------- | ------------------------------ |
| jt\_ad\_unit      | To specify the type of advertisement.                      | banner, interstitial, rewarded |
| jt\_ad\_sdk\_name | The SDK which served the advertisement.                    | Ironsource, Adjoe, Vungle      |
| jt\_ad\_network   | The ad network which served the advertisement.             | Ironsource, Adjoe, Vungle      |
| jt\_ad\_placement | Information related to the placement of the advertisement. | Level End, Game Finish, Shop   |

### Extra properties

| Parameter name | Description            | Suggested values |
| -------------- | ---------------------- | ---------------- |
| count          | The count of the event | 12345            |

## JtAdLoad

You can use this event to capture details of an event in which an advertisement is loaded to be served to the user.

### Default dimensions

| Name              | Description                                                | Suggested values               |
| ----------------- | ---------------------------------------------------------- | ------------------------------ |
| jt\_ad\_unit      | To specify the type of advertisement.                      | banner, interstitial, rewarded |
| jt\_ad\_sdk\_name | The SDK which served the advertisement.                    | Ironsource, Adjoe, Vungle      |
| jt\_ad\_network   | The ad network which served the advertisement.             | Ironsource, Adjoe, Vungle      |
| jt\_ad\_placement | Information related to the placement of the advertisement. | Level End, Game Finish, Shop   |

### Extra properties

| Parameter name | Description               | Suggested values      |
| -------------- | ------------------------- | --------------------- |
| duration       | The duration of the event | 12345                 |
| unit           | The unit of the duration  | seconds, milliseconds |

## JtAdOpen

You can use this event to capture details of an event in which an advertisement is opened.

### Default dimensions

| Name              | Description                                                | Suggested values               |
| ----------------- | ---------------------------------------------------------- | ------------------------------ |
| jt\_ad\_unit      | To specify the type of advertisement.                      | banner, interstitial, rewarded |
| jt\_ad\_sdk\_name | The SDK that served the advertisement.                     | Ironsource, Adjoe, Vungle      |
| jt\_ad\_network   | The ad network that served the advertisement.              | Ironsource, Adjoe, Vungle      |
| jt\_ad\_placement | Information related to the placement of the advertisement. | Level End, Game Finish, Shop   |

### Extra properties

| Parameter name | Description               | Suggested values      |
| -------------- | ------------------------- | --------------------- |
| duration       | The duration of the event | 12345                 |
| unit           | The unit of the duration  | seconds, milliseconds |

## JtAdShow

You can use this event to capture details of an event in which an advertisement is shown.

### Default dimensions

| Name              | Description                                                | Suggested values               |
| ----------------- | ---------------------------------------------------------- | ------------------------------ |
| jt\_ad\_unit      | To specify the type of advertisement.                      | banner, interstitial, rewarded |
| jt\_ad\_sdk\_name | The SDK which served the advertisement.                    | Ironsource, Adjoe, Vungle      |
| jt\_ad\_network   | The ad network which served the advertisement.             | Ironsource, Adjoe, Vungle      |
| jt\_ad\_placement | Information related to the placement of the advertisement. | Level End, Game Finish, Shop   |

### Extra properties

| Parameter name | Description            | Suggested values |
| -------------- | ---------------------- | ---------------- |
| count          | The count of the event | 12345            |

## JtAdStart

You can use this event to capture details of an event in which an advertisement is started.

### Default dimensions

| Name              | Description                                                | Suggested values               |
| ----------------- | ---------------------------------------------------------- | ------------------------------ |
| jt\_ad\_unit      | To specify the type of advertisement.                      | banner, interstitial, rewarded |
| jt\_ad\_sdk\_name | The SDK which served the advertisement.                    | Ironsource, Adjoe, Vungle      |
| jt\_ad\_network   | The ad network which served the advertisement.             | Ironsource, Adjoe, Vungle      |
| jt\_ad\_placement | Information related to the placement of the advertisement. | Level End, Game Finish, Shop   |

### Extra properties

| Parameter name | Description            | Suggested values |
| -------------- | ---------------------- | ---------------- |
| count          | The count of the event | 12345            |

## JtAdStop

You can use this event to capture details of an event in which an advertisement is stopped.

### Default dimensions

| Name              | Description                                                | Suggested values               |
| ----------------- | ---------------------------------------------------------- | ------------------------------ |
| jt\_ad\_unit      | To specify the type of advertisement.                      | banner, interstitial, rewarded |
| jt\_ad\_sdk\_name | The SDK which served the advertisement.                    | Ironsource, Adjoe, Vungle      |
| jt\_ad\_network   | The ad network which served the advertisement.             | Ironsource, Adjoe, Vungle      |
| jt\_ad\_placement | Information related to the placement of the advertisement. | Level End, Game Finish, Shop   |

### Extra properties

| Parameter name | Description            | Suggested values |
| -------------- | ---------------------- | ---------------- |
| count          | The count of the event | 12345            |

## JtButtonClick

You can use this event to capture details about a button that was clicked by the user.

### Default dimensions

| Name              | Description                                                     | Suggested values                  |
| ----------------- | --------------------------------------------------------------- | --------------------------------- |
| jt\_element\_name | You can use this dimension to specify which button was clicked. | Close Ad, Retry Level, Go to Shop |

## JtButtonShow

You can use this event to capture details about a button that was shown to the user.

### Default dimensions

| Name              | Description                                                   | Suggested values                  |
| ----------------- | ------------------------------------------------------------- | --------------------------------- |
| jt\_element\_name | You can use this dimension to specify which button was shown. | Close Ad, Retry Level, Go to Shop |

## JtCardClick

You can use this event to capture details about a card that was clicked by the user.

### Default dimensions

| Name              | Description                                                   | Suggested values |
| ----------------- | ------------------------------------------------------------- | ---------------- |
| jt\_element\_name | You can use this dimension to specify which card was clicked. |                  |

## JtCardShow

You can use this event to capture details about a card that was shown to the user.

### Default dimensions

| Name              | Description                                                 | Suggested values |
| ----------------- | ----------------------------------------------------------- | ---------------- |
| jt\_element\_name | You can use this dimension to specify which card was shown. |                  |

## JtDialogShow

You can use this event to capture details about a dialog that was shown to the user.

### Default dimensions

| Name              | Description                                                   | Suggested values                                             |
| ----------------- | ------------------------------------------------------------- | ------------------------------------------------------------ |
| jt\_element\_name | You can use this dimension to specify which dialog was shown. | Update Available, Invalid Credentials, Purchase Confirmation |

## JtLevelFail

You can use this event to track all details related to the level the user failed to complete.

### Default dimensions

| Name            | Description                                                                    | Suggested values                        |
| --------------- | ------------------------------------------------------------------------------ | --------------------------------------- |
| jt\_level\_name | You can use this dimension to specify which level the user failed to complete. | Level 1, Level 25, Boss 1, Dungeon Boss |

## JtLevelFinish

You can use this event to track all details related to the level the user cleared.

### Default dimensions

| Name            | Description                                                    | Suggested values                        |
| --------------- | -------------------------------------------------------------- | --------------------------------------- |
| jt\_level\_name | You can use this dimension to specify which level was cleared. | Level 1, Level 25, Boss 1, Dungeon Boss |

## JtLevelStart

You can use this event to track all details related to the level the user started to play.

### Default dimensions

| Name            | Description                                                         | Suggested values                        |
| --------------- | ------------------------------------------------------------------- | --------------------------------------- |
| jt\_level\_name | You can use this dimension to specify which level was being played. | Level 1, Level 25, Boss 1, Dungeon Boss |

## JtLogin

To capture all details related to user login events

### Default dimensions

| Name               | Description                          | Suggested values       |
| ------------------ | ------------------------------------ | ---------------------- |
| jt\_provider\_name | Could be used to record login method | email, facebook, gmail |

## JtNotificationClick

You can use this event to capture details about a notification that was clicked by the user.

### Default dimensions

| Name              | Description                                                           | Suggested values                                          |
| ----------------- | --------------------------------------------------------------------- | --------------------------------------------------------- |
| jt\_element\_name | You can use this dimension to specify which notification was clicked. | New Items Available, Special Offer, New Content Available |

## JtNotificationShow

You can use this event to capture details about a notification that was shown to the user.

### Default dimensions

| Name              | Description                                                         | Suggested values                                          |
| ----------------- | ------------------------------------------------------------------- | --------------------------------------------------------- |
| jt\_element\_name | You can use this dimension to specify which notification was shown. | New Items Available, Special Offer, New Content Available |

## JtPurchaseOptionClick

You can use this event to capture details of an event in which user clicks on purchase option.

### Default dimensions

| Name           | Description                                                                           | Suggested values                     |
| -------------- | ------------------------------------------------------------------------------------- | ------------------------------------ |
| jt\_item\_type | Use this dimension to categorize the item for which user showed interest to purchase. | In-App Currency, Weapon, Armor, Skin |
| jt\_item\_name | Name of the item can be provided in this dimension.                                   | Coins, Long Sword, Parry Shield      |
| jt\_item\_id   | ID of the item may be stored in this dimension                                        |                                      |

### Extra properties

| Parameter name | Description            | Suggested values |
| -------------- | ---------------------- | ---------------- |
| count          | The count of the event | 12345            |

## JtPurchaseOptionConfirm

You can use this event to capture details of an event in which user confirms purchase option.

### Default dimensions

| Name           | Description                                                                  | Suggested values                     |
| -------------- | ---------------------------------------------------------------------------- | ------------------------------------ |
| jt\_item\_type | Use this dimension to categorize the item for which user confirmed purchase. | In-App Currency, Weapon, Armor, Skin |
| jt\_item\_name | Name of the item can be provided in this dimension.                          | Coins, Long Sword, Parry Shield      |
| jt\_item\_id   | ID of the item may be stored in this dimension                               | 4561, 10, 2.1                        |

### Extra properties

| Parameter name | Description            | Suggested values |
| -------------- | ---------------------- | ---------------- |
| count          | The count of the event | 12345            |

## JtResourceSink

You can use this event to capture details of items removed from user's inventory. It could be either weapons or in-app currency.

### Default dimensions

| Name           | Description                                                                   | Suggested values                     |
| -------------- | ----------------------------------------------------------------------------- | ------------------------------------ |
| jt\_item\_type | Use this dimension to categorize the item deducted from the user's inventory. | In-App Currency, Weapon, Armor, Skin |
| jt\_item\_name | Name of the item can be provided in this dimension                            | Coins, Long Sword, Parry Shield      |
| jt\_item\_id   | ID of the item may be stored in this dimension                                | 4561, 10, 2.1                        |

### Extra properties

| Parameter name | Description            | Suggested values |
| -------------- | ---------------------- | ---------------- |
| count          | The count of the event | 12345            |

## JtResourceSource

You can use this event to capture details of items added to user's inventory. It could be either weapons or in-app currency.

### Default dimensions

| Name           | Description                                                              | Suggested values                     |
| -------------- | ------------------------------------------------------------------------ | ------------------------------------ |
| jt\_item\_type | Use this dimension to categorize the item added to the user's inventory. | In-App Currency, Weapon, Armor, Skin |
| jt\_item\_name | Name of the item can be provided in this dimension.                      | Coins, Long Sword, Parry Shield      |
| jt\_item\_id   | ID of the item may be stored in this dimension                           | 4561, 10, 2.1                        |

### Extra properties

| Parameter name | Description            | Suggested values |
| -------------- | ---------------------- | ---------------- |
| count          | The count of the event | 12345            |

## JtScreenShow

You can use this event to capture details about a screen that was shown to the user.

### Default dimensions

| Name              | Description                                                   | Suggested values                          |
| ----------------- | ------------------------------------------------------------- | ----------------------------------------- |
| jt\_element\_name | You can use this dimension to specify which screen was shown. | Main Menu, Level Complete, Items Unlocked |

## JtUserRating

To store user rating information

### Default dimensions

| Name              | Description                                                              | Suggested values  |
| ----------------- | ------------------------------------------------------------------------ | ----------------- |
| jt\_element\_name | Could be used to record the rating score provided or the user perception | 7, 8/10, positive |
