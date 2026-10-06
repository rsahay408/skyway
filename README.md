# SkyWay – demo airline app (hard-coded data)

## Get the APK (no local Android setup)
1. Create a new GitHub repo and push this folder (including `.github`).
2. Open the **Actions** tab -> "Build APK" (runs on push, or click *Run workflow*).
3. When finished, download artifact **skyway-debug-apk** -> unzip -> `app-debug.apk`.
4. Drag the APK onto an Android emulator (Android Studio AVD, Genymotion, BlueStacks) or `adb install app-debug.apk`.

## Build locally instead (needs Node 20, JDK 21, Android Studio/SDK)
    npm install
    npx cap add android
    npx cap sync android
    cd android && ./gradlew assembleDebug
    # APK: android/app/build/outputs/apk/debug/app-debug.apk

## Quick preview
Open `www/index.html` in a browser (use mobile view in dev tools).
