# ProfileCreator 0.2.3 (Beta 8)

Please report any bugs, feature requests or suggestions as an issue to this repository.

## New Features

### Dark Mode

This release has implemented support for the new Dark Mode feature in macOS Mojave.

Note:
    If you are using the default settings for code highlighting that will switch to it's dark equivalent when in Dark Mode.
    If you have customized your code highlighting that will not be changed when switching to Dark Mode.

### Simpler manifest arrays

When creating manifests, if you want to define a simple array without collection values you are now only required to specify the type and nothing else.

Previously one also had to include a key name even if that wasn't used.

### Notarization

The application is now Notarized by Apple.

## Updated Features

### Payload Filter

When using the payload filter (search) the application now shows matches for the PayloadType value as well as the DisplayName of the payload.


## New Preferences


## Updated Preferences

* Changed the default preference for `PayloadManifestsAutomaticallyDownloadUpdates` to `true`.
 This only applies when that setting has not been set in the user's preference file.

## New Payloads

* com.apple.eas.account (iOS)
* com.apple.systempolicy.managed (macOS)
* com.apple.security.FDERecoveryKeyEscrow (macOS)
* com.apple.security.FDERecoveryRedirect (macOS)

## Updated Payloads

### Configuration

*  `PayloadIdentifier` and `PayloadUUID` are now hidden by default as those created unneccesary confusion for people new to profiles. 
 If you know you need to change those, they can be showed again from the settings by enabling "hidden" keys.

* `PayloadScope` is now enabled by default as that is a setting that should be set for the profile and not just when exporting the profile.

### com.apple.systempreferences

* Changed scope to include User

### com.apple.airprint

* Added macOS as supported platform.

### com.apple.AssetCache.managed

* Fixed incorrect titles and added segmented control for better structure.

### com.apple.DirectoryService.managed

* Renamed payload from `Directory` to `Active Directory`.

### com.apple.domains

* Added macOS as supported platform for the `EmailDomains` key.

### com.apple.screensaver

* Added the key `idleTime` to the computer level screensaver payload.
* Added the key `moduleName` to the computer level screensaver payload.

### com.apple.ews.account

* Added new keys for OAuth supported in macOS 10.14.

### com.apple.loginwindow

* Fixed incorrect boolean value for key `SHOWFULLNAME`.
* Removed user scope as a valid export.

### com.apple.systempreferences

* Added the key `HiddenPreferencePanes`

### com.apple.systempolicy.contro

* Renamed from `Policy Control: System` to `System Policy: Control`

### com.apple.TCC.configuration-profile-policy

* Renamed from `Policy Control: Privacy` to `Privacy Preferences Policy Control`

### com.apple.dock

* Added the key `static-apps`. This key also supports drag and drop.
* Added the key `static-others`. This key also supports drag and drop.

### com.microsoft.Outlook

* Added new keys for versions 16.18 and 16.19

## Bug Fixes

* Fixed a bug where boolean to integer conversion failed for certain payload key values.
* Fixed a bug where you could not see or scroll to text that was outside the edge of the textfield.
* Fixed a bug where the UI would not always show the correct value for a range list that did not have custom titles set.
* Now payloads that don't have an icon set will use a generic dotted square as icon instead of empty space.
* Now the "Show Hidden" setting also shows tableview columns that were previously hidden.
* ...and many minor bug fixes. 

## Known Issues

* When a profile is repoened by the application at launch, the application doesn't recognize that it's open and multiple copies of the same profile may be open at the same time.

* When saving a profile for the first time, on rare occasions it might not save and won't be recognized after a restart.
(Never found a way to replicate, only rare reports. If this happens to you, please contact me or file an issue.)

## Contribute

There are many ways to contribute to this project. Here are a few listed below:

* Test and report bugs or incorrect behavior both in the UI and in the exported profiles.
* Language and spelling errors. (English is not my native language).
* Missing payloads or payload keys. (Contribute to the [ProfileManifests](https://github.com/erikberglund/ProfileManifests) repository to improve the manifests used to define all payloads, keys and their interactions.)
* Add feature requests or suggestions by opening an issue in this repository.
