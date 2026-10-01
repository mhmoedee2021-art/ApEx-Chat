<p align="center"><img src="assets/logo.png" width="260" alt="ApEx Chat"/></p>

<h1 align="center">ApEx Chat</h1>
<p align="center"><b>Professional Communication Platform by the ApEx Team</b><br/>
Developed by <b>Mahmoud Abdelrahman</b> · تم التطوير بواسطة <b>محمود عبدالرحمن</b></p>

---

## Features
- Email/password login, registration, password reset
- Profiles (name, photo) and online/offline presence
- Realtime 1-to-1 chat, replies, image messages, delete own messages
- Groups and Channels (admin-only posting), member/admin management
- 1-to-1 voice & video calls (WebRTC) with call history
- In-app message alerts, dark mode

## Tech
Flutter · Firebase Auth · Cloud Firestore · WebRTC — runs on the free Firebase Spark plan.

## Getting started
1. Follow [ANDROID_SETUP.md](ANDROID_SETUP.md) (add your own `google-services.json`, it is git-ignored).
2. Publish `firestore.rules` in the Firebase console.
3. ```bash
   flutter pub get
   dart run flutter_launcher_icons
   flutter run
   ```

## Limitations
See [README_FLUTLAB.txt](README_FLUTLAB.txt).

---
© ApEx Team — Developed by Mahmoud Abdelrahman
