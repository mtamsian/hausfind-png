# HausFind PNG — Android + installable web app

HausFind PNG is a starter prototype for a Papua New Guinea real-estate agency. It includes a searchable sample property catalogue, local viewing-request form, owner property-submission form, a basic agency desk, and CSV export in a web browser.

## What works now
- Filter the three illustrative sample listings by town/suburb, rent/sale, property type, budget, and bedrooms.
- Save viewing requests and owner submissions on the device/browser.
- Mark owner submissions as pending verification.
- Install the web version as a basic offline-capable PWA after it is hosted on HTTPS.
- Android Studio project that wraps the app in a simple Android WebView.

## Important limitations
- The sample properties and prices are fictitious examples, not real offers.
- Facebook is NOT connected. No automatic Facebook/group search, contact scraping, or Facebook messaging is implemented.
- No central server, staff login, multi-device syncing, email/SMS/WhatsApp notifications, payment processing, or real booking confirmation exists yet. Records are stored locally on one device/browser and can be lost if its app data is cleared.
- Before public launch, connect a secure backend, authentication and role-based permissions; build an authorised Meta integration where permitted; verify property ownership/authority; add real appointment notifications; and publish a real privacy policy and support contact.
- This source package does not contain a compiled APK/AAB or signing key. Build it with Android Studio first.

## Build the Android app
1. Install the current stable Android Studio from the official Android developer website.
2. Install Android SDK Platform 36 and a Java 17 JDK from Android Studio's SDK Manager.
3. Extract this ZIP to a writable folder.
4. In Android Studio choose **Open**, and select the extracted `hausfind_png` folder (the folder containing `settings.gradle`).
5. Allow Gradle sync to finish. Gradle 8.13 and Android Gradle Plugin 8.13.0 may be downloaded by Android Studio; an internet connection is needed for the first build.
6. To test on a connected Android phone, enable Developer options and USB debugging, then click **Run**.
7. To create a file for direct installation, choose **Build → Build APK(s)**. Android Studio will show the APK location. For Google Play, choose **Build → Generate Signed Bundle / APK → Android App Bundle**, create and safely back up a release signing key, and generate a signed `.aab`.

If Android Studio reports that the Gradle wrapper JAR is missing, create/open a new Android project in Android Studio and use its Gradle wrapper, or install Gradle and run `gradle wrapper --gradle-version 8.13` from this project directory, then reopen the project. This ZIP includes wrapper configuration but not the wrapper binary.

## Use the web app without publishing to Google Play
The `web/` folder contains a PWA version. Upload that folder to an HTTPS static host such as GitHub Pages. Open the hosted page in Chrome on Android and choose **Install app** or **Add to Home screen**. The website itself can be hosted for free on an eligible static-hosting service; custom domains and backend services may cost money. Service-worker offline caching works only when hosted over HTTPS (or localhost), not by opening the HTML file directly.

## Google Play publication
Google Play developer registration is not free: Google currently states a **US$25 one-time registration fee**, plus identity verification and possible testing requirements for new personal accounts. See the official guide: https://support.google.com/googleplay/android-developer/answer/6112435

An APK is normally for direct testing/installation. Google Play publication generally requires a signed Android App Bundle (AAB), a Play Console developer account, store listing assets, content rating, Data safety disclosures, privacy policy, and compliance with current Play policies. New personal developer accounts may need to complete a closed test before production access. Uploading this prototype does not guarantee approval.

## App identity
- Display name: HausFind PNG
- Android application ID: `com.hausfind.png` (change before release if you control a different unique namespace)
- Version: 1.0.0 (versionCode 1)

## Privacy baseline
The current Android prototype does not request network, contacts, location, camera, or microphone permissions. Viewing and owner-submission details are stored in local WebView storage on the device. The web version uses browser local storage. Do not use real customer data for production until a secure backend, access controls, data retention, deletion and privacy processes have been implemented.
