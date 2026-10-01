APEX CHAT — FLUTLAB PACKAGE (free plan, no payments)

Included:
- Firebase email/password login, registration, password reset
- Firestore user profiles (edit name, change photo), online/offline presence
- Realtime 1-to-1 chat + conversations list (last message + time)
- Groups (everyone can post) and Channels (only admins post); add/remove members, admins, rename, leave
- Images (stored inline in Firestore, no Cloud Storage), reply, delete own messages
- 1-to-1 voice and video calls (WebRTC, Firestore signaling) + call history
- In-app message alerts while the app is open
- Dark mode, settings

Setup: see ANDROID_SETUP.md. Rules: firestore.rules.

Limitations:
- No push notifications when the app is closed (needs a server; not free on Firebase).
- Group/channel calls not implemented (1-to-1 only).
- Incoming calls ring full-screen only while the app is open.
- Channels are invite-only; no public channel discovery.
- Calls may need a TURN server on some networks.
- Never put a Firebase Admin SDK key inside the Flutter app.
