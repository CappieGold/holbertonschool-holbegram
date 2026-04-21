# Holbegram

> Final Flutter project — Holberton School
> An Instagram-like mobile application built with Flutter, Dart, Firebase and Cloudinary.

**Author:** Jeremy Carpentier

---

## 📖 About the project

Holbegram is a social photo-sharing mobile app inspired by Instagram, developed as the final
Flutter project of the Holberton School curriculum.

Developing a mobile application that runs on both Android and iOS traditionally requires
maintaining two separate codebases in two different languages (Java/Kotlin for Android,
Objective-C/Swift for iOS). **Flutter** solves this problem by providing a single codebase
written in **Dart**, which renders the UI directly on the operating system's canvas for
native-like performance on both platforms.

This project is an opportunity to learn:

- The **Dart** language and asynchronous programming (`Future`, `async`/`await`, streams).
- The **Flutter** framework, its widget tree and its stateful/stateless components.
- How to integrate a **Firebase** backend (Authentication, Firestore database) into a Flutter
  application on Android and iOS.
- How to upload, store and deliver user media using **Cloudinary**.
- State management with the **Provider** pattern.

---

## 🧱 Tech stack

| Layer          | Technology                                                      |
|----------------|-----------------------------------------------------------------|
| Language       | Dart 3.x                                                        |
| Framework      | Flutter 3.x (stable channel)                                    |
| Authentication | Firebase Authentication (email / password)                      |
| Database       | Cloud Firestore                                                 |
| Media storage  | Cloudinary (unsigned upload preset)                             |
| State mgmt     | `provider`                                                      |
| Target OS      | Android (primary), iOS (via Xcode), Web (secondary)             |

### Main Flutter packages

- `firebase_core`, `firebase_auth`, `cloud_firestore` — Firebase integration
- `cloudinary_public` — media upload to Cloudinary
- `image_picker` — pick photos from gallery / camera
- `provider` — state management
- `uuid` — unique identifiers for posts
- `cached_network_image` — image caching with placeholder
- `flutter_staggered_grid_view` — Pinterest-style grid
- `pull_to_refresh` — swipe-down to refresh
- `bottom_navy_bar` — animated bottom navigation
- `cupertino_icons` — iOS-style icons

---

## 📁 Repository structure

```
holbertonschool-holbegram/
├── README.md            ← this file
└── holbegram/           ← Flutter project root
    ├── pubspec.yaml
    ├── lib/
    │   ├── main.dart
    │   ├── screens/     ← UI pages (login, signup, home, upload, profile…)
    │   ├── widgets/     ← reusable UI components
    │   ├── services/    ← Firebase / Cloudinary clients
    │   ├── providers/   ← shared application state
    │   ├── models/      ← data classes (User, Post…)
    │   └── utils/       ← colors, helpers
    ├── android/         ← native Android wrapper (Gradle)
    ├── ios/             ← native iOS wrapper (Xcode)
    └── web/             ← web entry point
```

---

## 🚀 Getting started

### Prerequisites

- [Flutter SDK](https://docs.flutter.dev/get-started/install) (stable channel)
- A [Firebase project](https://console.firebase.google.com/) named `holbegram`
- A [Cloudinary account](https://cloudinary.com/) with an unsigned upload preset
- For iOS: macOS + Xcode + CocoaPods
- For Android: Android Studio (or just the Android SDK command-line tools)

### 1. Clone the repository

```bash
git clone https://github.com/CappieGold/holbertonschool-holbegram.git
cd holbertonschool-holbegram/holbegram
```

### 2. Install the Flutter dependencies

```bash
flutter pub get
```

### 3. Configure Firebase

The Firebase configuration files are project-specific and must be obtained from your own
Firebase console.

**Android**

1. In the Firebase console, register an Android app with the package name
   `com.example.holbegram`.
2. Download the `google-services.json` file and place it in:
   ```
   holbegram/android/app/google-services.json
   ```

**iOS** (macOS only)

1. In the Firebase console, register an iOS app with the bundle ID `com.example.holbegram`.
2. Download `GoogleService-Info.plist`.
3. Open `holbegram/ios/Runner.xcworkspace` in Xcode and drag the `.plist` file into the
   `Runner` folder (check _Copy items if needed_ and _Add to target: Runner_).

### 4. Configure Cloudinary

Create an **unsigned** upload preset in the Cloudinary dashboard and note:

- your **cloud name**
- the **upload preset** name

These values are used by the Cloudinary client in `lib/services/`.

### 5. Run the application

```bash
# Web
flutter run -d chrome

# macOS desktop (quick test)
flutter run -d macos

# Android (emulator or physical device)
flutter run -d <device-id>

# iOS (physical iPhone or simulator, macOS only)
flutter run -d <device-id>
```

You can list the available devices with `flutter devices`.

---

## 🔧 Firebase setup checklist

Already performed on this project:

- [x] Firebase project `holbegram` created (Google Analytics disabled).
- [x] **Authentication** › Sign-in method › **Email/Password** enabled.
- [x] **Firestore Database** created in _test mode_ (security rules to be tightened later).
- [x] Android app registered with package `com.example.holbegram`.
- [x] `google-services.json` placed in `holbegram/android/app/`.
- [x] Google Services plugin wired in `android/settings.gradle.kts` and `android/app/build.gradle.kts`.
- [x] Firebase BoM (`firebase-bom:33.5.1`) imported at app level.
- [x] `Firebase.initializeApp()` called at the start of `lib/main.dart`.
- [ ] iOS app registered and `GoogleService-Info.plist` added (to be done on macOS).

---

## 🗺️ Roadmap

- [x] Project scaffold and dependency setup
- [x] Firebase Authentication and Firestore wiring
- [ ] Authentication screens (login / sign up)
- [ ] Home feed with posts from Firestore
- [ ] Upload screen with image picker and Cloudinary upload
- [ ] User profile with staggered grid of posts
- [ ] Search / discovery screen
- [ ] Likes and comments
- [ ] Pull-to-refresh on the feed

---

## 📚 Resources

- [Dart Cheatsheet](https://dart.dev/resources/dart-cheatsheet)
- [FlutterFire overview](https://firebase.flutter.dev/docs/overview)
- [Getting started with Firebase on Flutter](https://firebase.google.com/docs/flutter/setup)
- [Firebase Authentication on Flutter](https://firebase.flutter.dev/docs/auth/usage)
- [Cloudinary image upload (Flutter)](https://cloudinary.com/documentation/flutter_integration)
- [Layouts in Flutter](https://docs.flutter.dev/ui/layout)
- [Introduction to widgets](https://docs.flutter.dev/ui/widgets-intro)
- [Every Flutter Widget Explained](https://www.youtube.com/c/flutterdev)

---

## 👤 Author

**Jeremy Carpentier** — Holberton School student
GitHub: [@CappieGold](https://github.com/CappieGold)

---

## 📄 License

This project is developed as part of the Holberton School curriculum for educational
purposes.
