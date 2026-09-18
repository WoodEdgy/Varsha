VARSHA - Vedic Varshaphal Calculator (Android Project)
© Manik Roy 2026. All Rights Reserved.
================================================

WHAT THIS IS
A complete, ready-to-build Android app project (using Capacitor), wrapping
the exact same VARSHA web app interface in a native Android shell, using
your logo as the app icon.

IMPORTANT — WHY THERE'S NO .APK/.AAB FILE ALREADY IN HERE
Building a real Android app requires the Android SDK, build tools and
Gradle — all of which are hosted on Google's and Gradle's servers. The
sandbox this project was built in cannot reach those servers, so I
could not compile the final .apk/.aab myself. Everything else is done:
the native project, icons, manifest, and permissions are all fully
configured and ready to compile — it just needs an actual build step,
which you can do either of two ways below.

--------------------------------------------------------------
OPTION 1 (RECOMMENDED — no installs, builds in the cloud, free)
--------------------------------------------------------------
This project includes a ready-made GitHub Actions workflow
(.github/workflows/build-android.yml) that automatically builds a debug
APK, a release APK, and a release AAB every time you push this project
to GitHub.

1. Create a free GitHub account if you don't have one, and create a new
   (public or private) repository.
2. Upload this entire folder's contents to that repository (drag-and-drop
   on github.com works fine, or use git push if you're familiar with it).
3. Go to the "Actions" tab of your repository. A workflow run should
   start automatically (or click "Run workflow" to trigger it manually).
4. Wait a few minutes for it to finish (green checkmark).
5. Click into the finished run, scroll to "Artifacts", and download:
     - VARSHA-debug-apk        -> install this directly on any Android
                                   phone to test (see install notes below)
     - VARSHA-release-apk-unsigned -> smaller, optimized, but needs signing
                                   before installing on most devices
     - VARSHA-release-aab-unsigned -> the format the Google Play Store
                                   requires, also needs signing before
                                   upload

--------------------------------------------------------------
OPTION 2 (BUILD LOCALLY WITH ANDROID STUDIO)
--------------------------------------------------------------
1. Install Android Studio (free, from developer.android.com).
2. Open this project's "android" folder in Android Studio
   (File > Open > select the "android" folder).
3. Let it sync (first time may take a while as it downloads the SDK).
4. Build > Build Bundle(s) / APK(s) > Build APK(s) - or use
   Build > Generate Signed Bundle / APK for a signed release AAB ready
   for the Play Store.

--------------------------------------------------------------
ABOUT SIGNING
--------------------------------------------------------------
- The debug APK is already signed with a debug key and can be installed
  directly on any Android phone for testing (with "install from unknown
  sources" allowed in phone settings).
- A release APK/AAB must be signed with your own key before it can be
  installed on most phones or uploaded to Google Play. Android Studio's
  "Generate Signed Bundle / APK" wizard creates a signing key for you
  and handles this automatically - it's a guided, one-time process.

--------------------------------------------------------------
PROJECT DETAILS
--------------------------------------------------------------
App name:      VARSHA
Package ID:    com.manikroy.varsha
Min SDK:       set by Capacitor's default (Android 6.0+ devices)
Permissions:   INTERNET (needed for the free geocoding lookup)
Web content:   android/app/src/main/assets/public (this is the same
               app interface as the web/Windows versions - edit
               index.html in the "www" folder, then run
               "npx cap sync android" to update the native project.)
