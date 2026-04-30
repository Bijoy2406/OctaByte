<p align="center">
  <img src="assets/images/logo.png" alt="OctaByte Logo" width="220"/>
</p>

<h1 align="center">OctaByte</h1>

<p align="center">
  <b>Your All-in-One PC Building & Tech Marketplace</b><br/>
  <i>Built with Flutter · Powered by Firebase</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter&logoColor=white" alt="Flutter"/>
  <img src="https://img.shields.io/badge/Dart-%3E%3D3.2.3-0175C2?logo=dart&logoColor=white" alt="Dart"/>
  <img src="https://img.shields.io/badge/Firebase-Backend-FFCA28?logo=firebase&logoColor=black" alt="Firebase"/>
  <img src="https://img.shields.io/badge/Platform-Android%20%7C%20iOS%20%7C%20Web%20%7C%20Desktop-green" alt="Platform"/>
  <img src="https://img.shields.io/badge/License-Private-red" alt="License"/>
</p>

---

## 📖 Overview

**OctaByte** is a feature-rich, cross-platform Flutter application designed for PC enthusiasts, gamers, and tech shoppers. It combines a custom **PC Builder** tool, a peer-to-peer **Marketplace**, a social **Community** wall, and curated **Tutorials** — all wrapped in a sleek dark-themed UI with amber accents.

The app uses **Firebase** as its backend for authentication, real-time database, cloud storage, and push notifications, providing a seamless and responsive user experience.

---

## ✨ Features

### 🖥️ OctaBuilder — Custom PC Builder
- Browse and select components: **CPU, GPU, Motherboard, RAM, Storage, PSU**
- Add peripherals: **Monitor, Keyboard, Mouse, Headphones, Casing**
- Real-time price aggregation for your build
- Save builds to Firestore and view **Build History**
- Searchable component catalog with detailed specs

### 🛒 Octane — Marketplace
- Upload products for sale with image, name, price, and description
- Browse listings from all users in a real-time feed
- **In-app chat** between buyers and sellers
- View product details with integrated chat room
- Track **Purchase History** from your profile

### 💬 Octagram — Community Wall
- Post messages visible to all users in real-time
- Like and interact with community posts
- Timestamped feed sorted chronologically
- Signed-in user identity displayed per post

### 📚 Octahub — Tutorials
- Curated video tutorials for PC building and tech topics
- Integrated **Flick Video Player** for in-app playback
- Organized tutorial listings with thumbnail previews

### 🔔 Notifications
- **Firebase Cloud Messaging (FCM)** for push notifications
- **Local notifications** with custom payloads
- Contextual notifications triggered on feature navigation (e.g., welcome messages)
- Notification settings screen

### 👤 User Profile & Authentication
- **Firebase Authentication** (Email & Password)
- User registration with First Name, Last Name, Username, and Email
- Editable profile with **profile picture upload** (Firebase Storage)
- Forgot password flow with email reset
- Sign-out functionality

### 🎨 UI/UX Highlights
- Animated **Lottie splash screen** on app launch
- Dark-themed design with amber accent colors
- Bottom navigation bar with **Dashboard**, **Trending**, and **Profile** tabs
- Image carousels on the Trending screen (auto-play & manual control)
- Smooth page indicators and custom scaffolds
- Responsive layouts with `flutter_screenutil`

---

## 🏗️ Architecture

```
lib/
├── main.dart                     # App entry point & Firebase init
├── lottie.dart                   # Animated splash screen
├── navigation_menu.dart          # Bottom navigation controller
├── firebase_options.dart         # Firebase platform config
├── dp.dart                       # Display picture utilities
│
├── auth_screens/                 # Auth state management
│   ├── auth_page.dart            # Login/Register toggle
│   └── main_page.dart            # Auth state wrapper
│
├── interface_screens/            # Authentication UI
│   ├── login_page.dart           # Sign-in screen
│   ├── register_page.dart        # Registration screen
│   └── forgot_pw_page.dart       # Password reset screen
│
├── navibar_screens/              # Main tab screens
│   ├── dashboard_screen.dart     # Feature grid (Builder, Market, Community, Tutorials)
│   ├── trending_screen.dart      # Deals & banner carousels
│   ├── homepage_screen.dart      # User profile & settings
│   └── notification/             # Push & local notification services
│       ├── NotificationPage.dart
│       ├── firebase_api_noti.dart
│       ├── notificationService.dart
│       └── settings_screen.dart
│
├── dasboard_screens/             # Feature modules
│   ├── pc_builder/               # OctaBuilder
│   │   ├── core/                 # Component data (CPU, GPU, RAM, etc.)
│   │   ├── models/               # Component UI & detail screens
│   │   ├── pages/                # Builder screen, collection page, build history
│   │   └── peripheral/           # Peripheral accessories data
│   │
│   ├── marketplace/              # Octane Marketplace
│   │   ├── marketplace_screen.dart
│   │   ├── products/             # Product model, widgets, details
│   │   ├── chat/                 # In-app messaging (Chatbox, ChatPage)
│   │   └── buy/                  # Purchase history
│   │
│   ├── community/                # Octagram Social Wall
│   │   ├── community_screen.dart
│   │   ├── models/               # Wall post model
│   │   └── reWidgets/            # Post button & reusable widgets
│   │
│   └── tutorials/                # Octahub Tutorials
│       ├── tutorials_page.dart
│       ├── tutorials_screen.dart
│       └── tutorials_screen2.dart
│
├── reusable_widgets/             # Shared UI components
│   ├── custom_scaffold.dart
│   ├── custom_scaffold2.dart
│   ├── custom_scaffold3.dart
│   └── reusable_widget.dart
│
├── database/                     # Firestore abstraction
│   └── firestore.dart
│
└── utils/                        # Utility functions
    └── color_utils.dart
```

---

## 🛠️ Tech Stack

| Layer            | Technology                                                        |
| ---------------- | ----------------------------------------------------------------- |
| **Framework**    | Flutter 3.x (Dart ≥ 3.2.3)                                       |
| **Auth**         | Firebase Authentication                                           |
| **Database**     | Cloud Firestore                                                   |
| **Storage**      | Firebase Storage                                                  |
| **Messaging**    | Firebase Cloud Messaging + Flutter Local Notifications            |
| **State Mgmt**   | GetX (`get`) + Provider                                          |
| **Navigation**   | GetX routing + Material page routes                               |
| **Video**        | Flick Video Player + Video Player                                 |
| **Animations**   | Lottie                                                            |
| **UI**           | Google Fonts, Iconsax, Carousel Slider, Smooth Page Indicator     |
| **Image Picker** | `image_picker`                                                    |
| **Responsive**   | `flutter_screenutil`                                              |
| **Permissions**  | `permission_handler`                                              |
| **Reactive**     | RxDart                                                            |

---

## 🚀 Getting Started

### Prerequisites

- **Flutter SDK** ≥ 3.x ([Install Flutter](https://docs.flutter.dev/get-started/install))
- **Dart SDK** ≥ 3.2.3
- **Firebase CLI** ([Firebase setup](https://firebase.google.com/docs/flutter/setup))
- Android Studio / Xcode (for mobile) or Chrome (for web)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/XGNoir95/OctaByte.git
   cd OctaByte
   ```

2. **Install dependencies**
   ```bash
   flutter pub get
   ```

3. **Configure Firebase**

   The project includes a pre-configured `firebase_options.dart`. If you need to connect your own Firebase project:
   ```bash
   flutterfire configure
   ```
   Ensure the following Firebase services are enabled in your console:
   - **Authentication** (Email/Password provider)
   - **Cloud Firestore**
   - **Firebase Storage**
   - **Cloud Messaging**

4. **Run the app**
   ```bash
   # Android
   flutter run

   # iOS
   flutter run -d ios

   # Web
   flutter run -d chrome

   # Windows
   flutter run -d windows
   ```

### Generate App Icons

```bash
flutter pub run flutter_launcher_icons
```

---

## 📱 Supported Platforms

| Platform | Status |
| -------- | ------ |
| Android  | ✅      |
| iOS      | ✅      |
| Web      | ✅      |
| Windows  | ✅      |
| macOS    | ✅      |
| Linux    | ✅      |

---

## 🗂️ Firestore Collections

| Collection      | Description                              |
| --------------- | ---------------------------------------- |
| `users`         | User profiles (name, email, avatar URL)  |
| `Posts`          | Firestore Database posts                 |
| `User Posts`     | Community wall messages with likes       |
| `products`      | Marketplace product listings             |
| `builds`        | Saved PC build configurations            |

---

## 📸 App Flow

```
Splash Screen (Lottie Animation)
        │
        ▼
  Auth Gate (Login / Register)
        │
        ▼
  ┌─────────────────────────────────────┐
  │         Bottom Navigation           │
  │  ┌──────────┬──────────┬─────────┐  │
  │  │Dashboard │ Trending │ Profile │  │
  │  └──────────┴──────────┴─────────┘  │
  └─────────────────────────────────────┘
        │              │           │
        ▼              ▼           ▼
  ┌──────────┐  ┌───────────┐  ┌──────────────┐
  │PC Builder│  │ Carousels │  │ User Info     │
  │Marketplace│ │ Hot Deals │  │ Edit Profile  │
  │Community │  │ Flash Sale│  │ Purchase Hist │
  │Tutorials │  └───────────┘  │ Past Builds   │
  └──────────┘                 │ Notifications │
                               │ Sign Out      │
                               └──────────────┘
```

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is private and not published to pub.dev. All rights reserved.

---

<p align="center">
  <b>Built with ❤️ using Flutter & Firebase</b>
</p>
