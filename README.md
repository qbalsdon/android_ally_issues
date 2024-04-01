# Android Ally
Welcome to the Android Ally main page!

The tools are two-fold: The [Android Ally](#the-android-ally) and [TalkBack for Developers](#talkback-for-developers).

Watch the [YouTube introduction][12]

![Screenshot of the Android ally. It shows a connected device and some buttons for controlling TalkBack][102]

## The Android Ally

![Android Ally Logo][101]

The Android Ally is a desktop software companion to enable testers and developers faster access to Android device accessibility features. The core goal is to simplify and encourage Android Accessibility testing. It also works on emulators, which have been problematic because of the nature of the gestures that TalkBack uses.

The way that the software operates is by reading and writing values to the device settings through the Android Debug Bridge (ADB). On some devices, this may result in some unexpected behavior. Use at your own risk. Please read more about these commands from within the help menu. The Android Ally also has an optional Android accessibility service called TalkBack for Developers.

## TalkBack for Developers

![TalkBack For Developers Logo][100]

TalkBack is the [open source native screen reader for Android][4]. The two most popular versions are the base version from Google and the fork modified by Samsung. TalkBack for developers (TB4D) is a customized version of Google's TalkBack that allows developers to use [adb commands][5] for more fine-grained control of TalkBack. The core function is to allow developers to interact with TalkBack without having to learn complicated shortcuts and gestures. 

TalkBack for Developers (TB4D) allows for developer and tester oriented features whose goal is to speed up the development process. All TalkBack settings can be adjusted from the Android Debug Bridge (ADB) rather than having to navigate complex preference screens, which become even more difficult when TalkBack is active. Examples of the additional features include using the ADB to control TB4D:
 - navigate to the previous heading 
 > `adb shell am broadcast -a com.a11y.adb.previous -e mode headings`
 - navigate to the next heading 
 > `adb shell am broadcast -a com.a11y.adb.next -e mode headings`

TalkBack for developers comes bundled inside the Android Ally, and can be installed from the UI. If you want to side load it yourself, you may download the [phone APK][6] or the [wear APK][13].

### Advantages of TalkBack for Developers

- Simple installation on devices and emulators (emulators with Google API's are preferred)
- Complex navigation beyond simple tabbing
- Open the TalkBack menu with a button click
- Allow faster testing of custom actions
- Open TalkBack settings quickly

## About

Android accessibility is difficult for a number of reasons:
1. Design and QA communication can sometimes be hard to effectively diagnose
2. Accessibility training is difficult find, and finding time can be problematic as well
3. Accessibility documentation is always separate from core documentation - and in most example code, not present
4. Businesses do not understand usability / accessibility as a priority
5. Settings are scattered all over the system, and are modified in different ways
   - night mode has a useful `cmd` command alternative which is immediate, unlike using the (more well known, but not by much) settings API
   - color inversion is direct and immediate, color correction needs to be enabled and then changed
   - animations have 3 different values that users can only toggle with one control, even though they can scale internally
6. All assistive tech is user-first, with little to no considerations for the developers who need to implement features for it
7. Assistive tech is difficult to use while debugging
8. Assistive tech is difficult to learn in the context of getting the whole job done
9. Changing settings takes a long time, and even doing it by [ADB][5] doesn't always refresh immediately
10. The people most negatively impacted by engineers not being able to use accessibility tools are the users

# Requirements

## Computer

- A Java Runtime Environment
- The Android Debug Bridge (ADB):
  - [installed on your computer][8]
  - set up as a [path variable (Mac)][11] or as an [environment variable (Windows)][10]

## Phone / Emulator

- [Enable the Android Debug Bridge (ADB) on your phone][7]
- Google API's are recommended for emulators

# Downloads

- [Mac OSX Arm][0]
- [Mac OSX Intel][1]
- [Windows][2]
- [Debian Linux][3]

# Installation

Download the relevant package and unzip the installer.

> If you intend to control TalkBack with the on screen controls, you will need to install [TalkBack for Developers](#talkback-for-developers) - this can be done from the [Android Ally](#the-android-ally)


## Mac OSX

1. Open the DMG file and accept the license terms
2. Drag the App into your applications directory
3. From Applications, double click the app - it will tell you it's from an unverified developer. Select Cancel.
4. From Applications, right click the app and choose open, then select open from the dialog. You should only need to do this once

# Raising an issue

Issues will be handled at the discretion of the creator. It is highly recommended in the creation of an issue that you include:

1. The version of the Android Ally
2. Device information
  - Manufacturer: `adb shell getprop ro.product.manufacturer`
  - Model: `adb shell getprop ro.product.model`
  - Version: `adb shell getprop ro.build.version.release`
  - SDK level: `adb shell getprop ro.build.version.sdk`
  - User list: `adb shell pm list users`
  - Check if "Disable permission monitoring" is enabled in developer settings (it needs to be on)
3. Steps to reproduce
4. Expected behavior
5. Actual behavior

[0]: https://www.ally-keys.com/android_ally_desktop/Android_A11y_ARM_8_public.dmg.zip 
[1]: https://www.ally-keys.com/android_ally_desktop/Android_A11y_x64_8_public.dmg.zip 
[2]: https://www.ally-keys.com/android_ally_desktop/Android_A11y_8_public.msi.zip 
[3]: https://www.ally-keys.com/android_ally_desktop/Android_A11y_8_public.deb.zip 
[6]: https://www.ally-keys.com/android_ally_desktop/app-phone-signed-79.apk.zip
[13]: https://www.ally-keys.com/android_ally_desktop/app-wear-signed-79.apk.zip

[4]: https://github.com/google/talkback
[5]: https://developer.android.com/tools/adb
[7]: https://developer.android.com/studio/command-line/adb#Enabling
[8]: https://developer.android.com/studio/releases/platform-tools
[9]: https://stackoverflow.com/questions/17901692/set-up-adb-on-mac-os-x
[10]: https://doc.e.foundation/pages/install-adb-windows#adding-adb-path-to-the-environment-variables
[11]: https://stackoverflow.com/questions/17901692/set-up-adb-on-mac-os-x
[12]: https://www.youtube.com/watch?v=zoLLVzm8nzA

[100]: /images/icon_tb4d_round.png "TalkBack for developers"
[101]: /images/icon_aa_round.png "Android Ally"
[102]: /images/screenshot.png "Android Ally Screenshot"