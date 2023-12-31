# Changelog

## Version 4.5.0 (12th December 2023)

### Changed

* Updated Android SDK to 4.5.0.
* Updated iOS SDK to 4.5.0.
* The `UserEvent` classes have been changed such that you can now submit named custom dimensions instead of dimensions custom1/2/3.
* All predefined event classes have been renamed, some have been removed or merged. See the migration guide you received for more details.
* `JustTrackSDK.ForwardAdImpression` now requires you to construct an `AdImpression` object instead of passing individual parameters.
* The support for using Gradle templates was improved.

## Version 4.4.1 (30th August 2023)

### Changed

* Updated Android SDK to 4.4.1.
* Updated iOS SDK to 4.4.1.
* The IronSource integration now uses `GetUserId` instead of `GetAttribution`, completing the integration faster.
* The SDK no longer uses preprocessor defines to select available features at runtime (reducing the amount of pauses because of recompiling during development of an app or game).

### Bug-Fixes

* Manually integrating with IronSource twice no longer results in duplicated events.

## Version 4.4.0 (14th July 2023)

### Added

* `JustTrackSDK.GetUserId` was added to retrieve the justtrack user id in a callback.

### Changed

* Updated Android SDK to 4.4.0.
* Updated iOS SDK to 4.4.0.
* The justtrack SDK now provides the user and test group id without waiting for the justtrack backend.
* `JustTrackSDK.GetAffiliateLink` was renamed to `JustTrackSDK.CreateAffiliateLink`.
* `JustTrackSDK.PublishFirebaseAppInstanceId` was renamed to `JustTrackSDK.SetFirebaseAppInstanceId`.
* XCode 14.0 or newer is now required to build on iOS.

### Bug-Fixes

* A potential deadlock has been removed upon initialization.

## Version 4.3.8 (29th March 2023)

### Added

* `SetAutomaticInAppPurchaseTracking` was added to configure automatic in-app purchase tracking. It is enabled by default.

### Changed

* Updated Android SDK to 4.3.8.
* Updated iOS SDK to 4.3.8.

### Removed

* You can now no longer manually forward in-app purchases. Use the automatic integration instead.

## Version 4.3.7 (17th March 2023)

### Changed

* Updated Android SDK to 4.3.7.
* Updated iOS SDK to 4.3.7.

### Bug-Fixes

* Fixed a crash caused by multiple callbacks from Java to C# at the same time.

## Version 4.3.6 (2nd March 2023)

### Added

* The SDK can now integrate with AdColony, AppLovin, Chartboost, and Unity Ads.

### Changed

* Updated Android SDK to 4.3.6.
* Updated iOS SDK to 4.3.6.
* Renamed `AdUnit` to `AdFormat`, added more options and added ability to forward arbitrary ad formats as well.

### Bug-Fixes

* Fixed handling of Java classes and objects on C# side to deterministically free their resources again.

## Version 4.3.5 (16th December 2022)

### Changed

* Updated Android SDK to 4.3.5.
* Updated iOS SDK to 4.3.5.
* You no longer need to manually supply the receipt data as token on iOS to track in-app purchases.

## Version 4.3.4 (6th December 2022)

### Added

* The SDK now provides a method to track in-app purchases.

### Changed

* Updated Android SDK to 4.3.4.
* Updated iOS SDK to 4.3.4.
* You can now attach a currency to the events you are sending.
* If you are forwarding ad impressions, you now have to specify the currency for the revenue of the event.

## Version 4.3.3 (11th November 2022)

### Added

* The SDK now provides a function `JustTrackSDK.SetCustomUserId` to forward a custom user id to the justtrack backend.

### Changed

* Updated Android SDK to 4.3.3.
* Updated iOS SDK to 4.3.3.
* The iOS SDK is now integrated by including CocoaPod dependencies instead of distributed with the Unity version of the SDK.
* The GameObject of the SDK now removes its parent GameObject (if any) as it needs to mark itself as DontDestroyOnLoad (which requires that there is no parent).

### Bug-Fixes

* Requesting the tracking permission multiple times no longer publishes the corresponding tracking events multiple times.

## Version 4.3.2 (4th August 2022)

### Changed

* Updated Android SDK to 4.3.2.
* Updated iOS SDK to 4.3.2.
* The setting for the tracking provider was simplified and is now called attribution provider.
* Appsflyer is no longer required on iOS.
* The SDK now provides a method `ForwardAdImpression` to report ad impressions to the justtrack backend.
* The SDK now validates the configuration on build time and fails the build if invalid settings are detected.

### Bug-Fixes

* Fixed a bug which would cause the SDK to lose its configuration upon upgrade.

## Version 4.3.1 (7th July 2022)

### Changed

* Updated Android SDK to 4.3.1.
* Updated iOS SDK to 4.3.1.

### Bug-Fixes

* The SDK now stores internal logs and metrics more carefully to avoid excessive memory usage.

## Version 4.3.0 (6th May 2022)

### Changed

* The SDK now handles timeouts while collecting information for a correct attribution better. This will make it more likely to receive an attribution event (after the initial callback resolves) should you have registered a listener.
* Updated Android SDK to 4.3.0.
* Updated iOS SDK to 4.3.0.

## Version 4.2.9 (31st March 2022)

### Changed

* Renamed all occurrences of the Firebase instance id to Firebase app instance id. For example, `PublishFirebaseInstanceId` is now called `PublishFirebaseAppInstanceId`.
* Updated Android SDK to 4.2.9.
* Updated iOS SDK to 4.2.9.

### Bug-Fixes

* The code generated by the justtrack SDK is now marked `Preserve`, preventing it from getting stripped by too aggressive code optimization.

## Version 4.2.8 (30th March 2022)

### Added

* Added `JustTrackSDK.OnTrackingAuthorization` to query for the status of the tracking permission.
* The SDK can now automatically detect the Firebase instance id of a user and send it to the justtrack backend.

### Changed

* Updated Android SDK to 4.2.8.
* Updated iOS SDK to 4.2.8.
* The SDK now verifies the validity of an Api token in the Unity editor.
* The SDK now verifies that you are using the External Dependency Manager for Unity. If it doesn't find it, it shows a warning and assists you in adding it to your game.

## Version 4.2.6 (11th February 2022)

### Changed

* Updated Android SDK to 4.2.6.
* Updated iOS SDK to 4.2.6.

## Version 4.2.5 (17th December 2021)

### Added

* The SDK now provides an easy way to request permission to track a user on iOS.

### Changed

* Updated Android SDK to 4.2.5.
* Updated iOS SDK to 4.2.5.

## Version 4.2.4 (11th November 2021)

### Added

* The SDK now provides methods to get the advertiser id of the user and the test group id of the user.

### Changed

* Updated Android SDK to 4.2.4.
* Updated iOS SDK to 4.2.4.
* The SDK now includes logic to retry fetching the attribution if it failed last time and some time has passed.

## Version 4.2.3 (24th August 2021)

### Changed

* The SDK now automatically handles a network reconnect when fetching an attribution.
* Updated Android SDK to 4.2.3.
* Updated iOS SDK to 4.2.3.
* Refactored the settings of the SDK. They are now stored as a resource, so you can instantiate the SDK at runtime.
* There is now only one API token per platform instead of one for development and release.

## Version 4.2.2 (29th July 2021)

### Added

* The SDK now adds the justtrack backend as a receiver for SDKAdNetwork attribution postbacks (for iOS 15).

### Changed

* Updated Android SDK to 4.2.2.
* Updated iOS SDK to 4.2.2.

## Version 4.2.1 (1st July 2021)

### Bug-Fixes

* Fixed a missing parameter when constructing standard events with a unit for Android.

## Version 4.2.0 (25th June 2021)

### Changed

* Events tracking the progress of a user for a level or quest have been extended to automatically track the progress of the user and provide the duration the app was active during that time upon completion.
* The SDK no longer requests the `READ_PHONE_STATE` and `ACCESS_WIFI_STATE` permissions on Android.
* The session id is now included in all events sent to the backend.
* Setting a tracking id now also requires you to name the provider of that tracking id.

### Removed

* Removed `setRealTime` from all interfaces again as well as realTime event functionality.
* It is no longer possible to set the duration for progression events by hand.

### Bug-Fixes

* The SDK will now suggest you add some small generated code to work around limitations of the IL2CPP compiler to integrate with IronSource.

## Version 4.1.2 (27th May 2021)

### Removed

* Removed the external dependency manager from Google as dependency as Google removed their scoped registry. You have to provide a version of it now yourself.

## Version 4.1.1 (21st May 2021)

### Changed

* Fixed bad version constraint for dependency.

## Version 4.1.0 (19th May 2021)

### Changed

* Updated Android SDK to 4.1.1.
* Updated iOS SDK to 4.1.0.

## Version 4.0.1 (30th April 2021)

### Changed

* Updated Android SDK to 4.0.1.

### Bug-Fixes

* Fixed predefined events to publish their custom parameters with the correct dimensions.

## Version 4.0.0 (28th April 2021)

### Added

* Added `AttributionCampaign`, `AttributionChannel`, `AttributionNetwork` classes and changed the representation of an attribution slightly.
* Added `CustomUserEvent`, `Dimension`, `EventDetails`, `StandardUserEvent`, and `UserEvent` classes, enums, and interfaces.
* Added support for retargeting attributions. You can now get a new attribution if a user clicks on a retargeting campaign while your game is already running.

### Changed

* Updated Android SDK to 4.0.0.
* `AttributionResponse` and `AttributionRecruiter` now carry additional fields.
* Renamed `Units` to `Unit`.
* `PublishEvent` now accepts a string, an instance of `EventDetails`, or a complete `UserEvent`.
* Predefined events are now represented by classes instead of constants.

### Removed

* Removed AttributionNamed class.

## Version 2.4.5 (14th March 2021)

### Changed

* Added support to provide the SDK as a Unity package.

## Version 2.4.4 (3rd March 2021)

### Bug-Fixes

* Initialize the correct SDK agent when running in the editor.

## Version 2.4.3 (20th January 2021)

### Bug-Fixes

* Avoid initializing the SDK multiple times at the same time.

## Version 2.4.2 (12th January 2021)

### Added

* Added Appsflyer integration. You can now select a tracking provider per platform and the SDK will take care of the rest.
* Added field to query whether IronSource was already initialized.

### Changed

* Merged both prefabs into single prefab and extended logic to take care of all integration logic automatically.
* Updated Android and iOS SDKs to 2.4.2.

### Bug-Fixes

* Correctly forward IronSource ad impressions on Android.

***
