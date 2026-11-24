# Pulse Android App — Starter Project

This project packages your existing `pulse.html` website as an Android app using Capacitor.

## Included
- Your original Pulse interface and note/reminder features.
- Capacitor Android project setup.
- Native Android local-notification bridge for upcoming reminders.
- Vite build configuration.
- Existing browser storage is preserved for this first conversion.

## Before you start
Install:
1. Node.js LTS (choose the LTS release from https://nodejs.org/)
2. Android Studio (https://developer.android.com/studio)
3. Android SDK components offered by Android Studio.

Restart Windows after installing Node.js if the terminal does not recognise `node` or `npm`.

## Step-by-step on Windows

1. Extract this ZIP to a simple folder, for example `C:\PulseAndroid`.
2. Open that folder in File Explorer.
3. Click the address bar, type `cmd`, and press Enter.
4. Check Node.js:
   ```bash
   node -v
   npm -v
   ```
5. Install the project packages:
   ```bash
   npm install
   ```
6. Create the Android project:
   ```bash
   npx cap add android
   ```
7. Build the website and copy it into Android:
   ```bash
   npm run android:sync
   ```
8. Open the Android project:
   ```bash
   npx cap open android
   ```
9. In Android Studio, wait for Gradle sync to finish.
10. Connect your Android phone with USB debugging enabled, or create an emulator.
11. Press the green Run ▶ button and select your device.

## Whenever you change the website code
Run:
```bash
npm run android:sync
```
Then press Run again in Android Studio.

## Generate an APK
In Android Studio, choose:
`Build > Build Bundle(s) / APK(s) > Build APK(s)`

Android Studio will show a notification with a link to the generated APK.

## Important notes
- This is the first Android conversion, not yet a cloud-synced multi-device app.
- Notes are still stored locally on the device/browser WebView. Do not clear app storage or uninstall the app before exporting a backup.
- The native notification bridge schedules the next upcoming reminder notifications. Android notification permissions must be granted.
- Exact delivery time can depend on Android version, battery optimisation and the user's alarm/notification settings. Android 12+ may require exact-alarm access for strict clock-time delivery; this is subject to Android policy and user settings.
- Repeating reminders are advanced in the existing Pulse app logic when the app is opened and the reminder is completed. We can improve background recurrence and persistence in a later step.
- Test notifications on a real phone. Some emulator images do not behave exactly like physical devices.

## Next upgrades we can build
1. SQLite database instead of localStorage.
2. Reliable recurring reminders and rescheduling after device restart.
3. App lock / biometric unlock.
4. Cloud backup and account sync.
5. Widgets, calendar view and better notification actions.
