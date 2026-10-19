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

## Offline features
- **Flight status:** search 10 sample flights by flight number, city or airport code.
- **Boarding passes:** two demo passes in Economy and Business.
- **Find flights:** filter the sample timetable by origin, destination and cabin.
  Results show INR fares for one adult, sorted cheapest first; cancelled flights
  are excluded. This is not a date-based search or a real booking service.
- **Choose seat:** interactive Economy and Business seat maps with occupied seats.
  Choices update the boarding pass and are saved on the device using local
  storage. If storage is unavailable, an explicit warning explains that changes
  last only for the current session.
- **Baggage calculator:** domestic/international allowances for both cabins,
  with sample excess-baggage fees rounded up to the next whole kilogram.
- **Airport guide:** eight airports with sample terminals, lounges, amenities,
  transport information and travel tips.

All data is bundled with the app. Schedules, boarding-pass dates, prices, policies
and airport details are fictional/static demo information, not live travel advice.
No backend, account, real reservation, check-in or payment is involved.
After changing web assets, run `npx cap sync android` before building the APK.
