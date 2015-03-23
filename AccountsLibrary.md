| **Note**: This library targets obsolete versions of the Android platform. Most applications should use the [android.account](http://developer.android.com/reference/android/accounts/package-summary.html) APIs directly. |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

### Introduction ###

The package `com.google.android.accounts` mirrors the [accounts API](http://developer.android.com/reference/android/accounts/package-summary.html) that was introduced in [Android 2.0](http://developer.android.com/sdk/android-2.0.html).  It provides a fall-back implementation for [Android 1.5](http://developer.android.com/sdk/android-1.5.html) and [Android 1.6](http://developer.android.com/sdk/android-1.6.html), and makes it easier to implement new authenticators.  The library also includes basic support for implementing sync adapters.

### Interface ###

The API is modeled after the [android.accounts API](http://developer.android.com/reference/android/accounts/package-summary.html).  In many cases, migrating applications between `com.google.android.accounts` and `android.accounts` should simply be a matter of changing the imports.  However, there are a couple of differences worth noting:
  1. Parameters of type `Activity` are not supported by the methods in `AccountManager`.  Callers should manually invoke the `Intent` contained in the `Bundle` passed to the callback, e.g.,
```
Intent intent = bundle.getParcelable(AccountManger.KEY_INTENT);
startActivityForResult(intent, MY_REQUEST_CODE);
```
  1. The class `com.google.android.accounts.ContentSyncer` provides sync-related methods that were introduced as static methods of `ContentResolver` in [Android 2.0](http://developer.android.com/sdk/android-2.0.html), including `setIsSyncable(Account, String, int)`, `getIsSyncable(Account, String)`, `setSyncAutomatically(Account, String, boolean)`, `getSyncAutomatically(Account, String)`, and `requestSync(Account, String, Bundle)`.

### Authenticators ###

`DatabaseAuthenticators` store and provide authentication tokens, and provide `Parcelable` `Intents` for `Activities` that can be used to register new accounts or obtain authentication tokens.

`DatabaseAuthenticators` are used on all platform versions to implement new authenticators.  On older platforms that do not have the `android.accounts` API, the authenticators are also used to store sync settings (in the same database that is used to store authentication tokens).

For implementing new authenticators, please see the javadoc for `com.google.android.accounts.DatabaseAuthenticator`.

### Downloads ###
  * [accounts.jar](http://downloads.libs-for-android.googlecode.com/git/accounts.jar)