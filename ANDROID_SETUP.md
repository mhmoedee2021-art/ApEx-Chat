# Setup — 100% free (Firebase Spark plan, no card needed)

Used: Firebase Auth, Cloud Firestore, WebRTC (free public STUN). NOT used (they need a paid plan):
Cloud Storage, Cloud Functions.

## 1. Firebase (Spark plan)
1. Put `google-services.json` in `android/app/` (package must match `applicationId`, e.g. com.example.despatcher_app).
2. Authentication → enable Email/Password.
3. Firestore → create database → Rules tab → paste `firestore.rules` → Publish.

## 2. Gradle
- `android/app/build.gradle(.kts)`: apply plugin `com.google.gms.google-services`, `minSdk = 23` (flutter_webrtc needs 23+).
- `android/settings.gradle(.kts)`: plugin `com.google.gms.google-services` version `4.4.2`+ with `apply false`.

## 3. AndroidManifest.xml (inside <manifest>)
```xml
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.CAMERA"/>
<uses-permission android:name="android.permission.RECORD_AUDIO"/>
<uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="android.permission.BLUETOOTH" android:maxSdkVersion="30"/>
<uses-permission android:name="android.permission.BLUETOOTH_CONNECT"/>
<uses-feature android:name="android.hardware.camera" android:required="false"/>
<uses-feature android:name="android.hardware.camera.autofocus" android:required="false"/>
```

## How it stays free
- Images are resized and stored inside Firestore as base64 (chat images ≤ 600 KB, avatars ~200 px).
- Notifications are in-app banners while the app is open (Firestore realtime). No push server.
- Spark limits (about 50k reads / 20k writes per day, 1 GiB stored) are fine for a small app; heavy image
  traffic uses them up faster.

## Optional later
- Push when the app is closed: needs a server that calls FCM. A free option is a Cloudflare Workers script;
  ask and it can be added.
- Calls use only STUN. If calls connect with no audio/video on some networks, add a TURN server in
  `lib/call_service.dart` → `_rtcConfig`.

## Branding
- In `AndroidManifest.xml` set `android:label="ApEx Chat"` on the `<application>` tag.
- Generate launcher icons: `flutter pub get && dart run flutter_launcher_icons`.
