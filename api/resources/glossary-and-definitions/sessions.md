# Sessions

A session starts either when the app starts for the first time or comes back to the foreground after some inactivity.

As long as a user is interacting with an app and events are triggered the session for that particular user continues.

A session ends in one if the following three cases

* The app was in the background for a preconfigured timeframe, which can be changed in the justtrack dashboard and is set to 1 minute by default.
* We did not receive any events from a user for a preconfigured timeframe, which can be changed in the justtrack dashboard and is set to 30 minutes by default.
* In this case, the 30 minutes do not count towards the session length.
* The session ends at the time we received the last event.
* Every session ends at midnight to make sure the time spent in the app is counted towards the day at which it occurred.
* If we receive a new event after midnight, a new session will start.

Once the session ends, justtrack will calculate the total length of the session.

Note that it may take up to 2.5 hours after session end until **Average Time Spend in App** and the **Average Session Length** are updated on the justtrack dashboard.
