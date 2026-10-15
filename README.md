# LB Agriconnect — Offline + Online Android starter

This is **Milestone B / Sprint 1**: an Android starter project for an offline-first agricultural marketplace.

## Included
- Kotlin + Jetpack Compose screens
- Room local database for product listings and draft records
- Local-first save flow (usable without internet)
- WorkManager network-constrained sync
- Firebase Firestore upload path for pending products and records
- Role dropdown: Farmer, Agronomist, Transporter, Wholesaler, Vendor, Consumer, FarmFin

## Before building
1. Install Android Studio with JDK 17 and Android SDK 35.
2. Open this folder in Android Studio and allow Gradle sync.
3. Create a Firebase project at https://console.firebase.google.com/.
4. Add an Android app with package name `com.lb.agriconnect`.
5. Download `google-services.json` and place it inside the `app/` folder.
6. Enable Firestore in Firebase Console. Configure Firebase Authentication before enabling real user accounts.
7. Add Firestore security rules before using real data. Do not deploy with open read/write rules.

## Build an APK
In Android Studio: **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
The debug APK is usually created at `app/build/outputs/apk/debug/app-debug.apk`.

Or use a terminal with JDK 17 and Android SDK installed:
```bash
./gradlew assembleDebug
```

## Important prototype limitations
- This starter synchronizes local pending records to Firestore, but does not yet download/merge the shared marketplace catalogue from Firestore.
- Authentication, permissions, payment processing, transport dispatch, conflict resolution, and full role-specific profiles are not implemented yet.
- A product is marked synced after Firestore confirms its upload. An offline order draft is **not** a confirmed order.
- Add `google-services.json` locally; it is intentionally not included because it is specific to your Firebase project.
- Test sync and security rules before using real customer or business data.
