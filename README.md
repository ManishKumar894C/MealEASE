# 🍲 MealEASE - Smart Mess & Hostel Dining Management System

[![Android](https://img.shields.io/badge/Platform-Android-green.svg?logo=android)](https://developer.android.com)
[![Kotlin](https://img.shields.io/badge/Language-Kotlin-purple.svg?logo=kotlin)](https://kotlinlang.org)
[![Jetpack Compose](https://img.shields.io/badge/UI-Jetpack%20Compose-4285F4.svg?logo=jetpackcompose)](https://developer.android.com/jetpack/compose)
[![Firebase](https://img.shields.io/badge/Backend-Firebase-FFCA28.svg?logo=firebase)](https://firebase.google.com)
[![Room](https://img.shields.io/badge/Database-Room%20DB-4285F4.svg)](https://developer.android.com/training/data-storage/room)

**MealEASE** is an end-to-end Smart Mess Management Android Application designed for hostels, educational institutions, and corporate dining halls. It streamlines meal attendance forecasting, reduces food wastage, automates billing and ledger dues, and provides a seamless role-based interface for Students, Mess Managers, and Staff.

---

## 🌟 Key Features & Role Capabilities

### 🎓 1. Student Portal
* **Weekly Menu Explorer**: Interactive schedule of daily Breakfast, Lunch, and Dinner options.
* **Smart Meal Skip**: Toggle individual meal slots (Lunch / Dinner) or full-day skips to automatically adjust dues and notify the kitchen.
* **Digital Ledger & Dues**: View real-time dues summary, skipped meal rebates.
* **Meal Rating & Feedback**: Rate daily meals (Kadhi, Rice, Roti) to help improve food quality.
* **Support Desk**: Lodge support tickets for maintenance/hygiene issues with history tracking and single/bulk delete options.
* **Campus Notices & Notifications**: Stay updated with priority announcements from mess management.

---

### 👨‍🍳 2. Manager & Admin Dashboard
* **Live Attendance & Skip Forecast**: Real-time aggregation of student meal skip responses to minimize kitchen over-preparation and food wastage.
* **Menu Schedule Editor**: Edit and update daily meal menus with global synchronization across all student devices.
* **Leftover Log & Waste Analytics**: Record and monitor daily leftover food items to optimize raw ingredient purchasing.
* **Resolution Desk**: Manage student support tickets, update status (*Pending*, *In Progress*, *Resolved*), and reply directly to students.
* **Billing & Dues Management**: Track student payment statuses, send automated payment reminders, and export audit reports.
* **Account Credentials Management**: Provision and manage Student and Staff ID credentials.

---

### 🎟️ 3. Staff & Kitchen Desk
* **QR Coupon Scanner & Verification**: Validate and redeem student guest passes using code queries or QR validation.
* **Kitchen Production Adjustments**: View exact student headcounts per meal slot for accurate cooking volumes.

---

## 🏗️ Architecture & Tech Stack

MealEASE is built following modern Android development best practices with an offline-first architecture:

* **Language**: Kotlin 2.2
* **UI Toolkit**: Jetpack Compose with Material 3 UI Design System & Custom Themes
* **Architecture Pattern**: MVVM (Model-View-ViewModel) + Unidirectional Data Flow (UDF)
* **Asynchronous Operations**: Kotlin Coroutines & `StateFlow` with `collectAsStateWithLifecycle()`
* **Local Persistence**: **Room Database** (offline-first caching for menus, ledger, tickets, notices, coupons)
* **Cloud Sync & Backend**: **Cloud Firestore** for global synchronization & **Firebase Auth / Credential Manager** for authentication
* **Dependency Injection & Build**: Gradle KSP (Kotlin Symbol Processing), AndroidX Libraries

---

## 📂 Project Structure

```text
app/src/main/java/com/example/
├── MainActivity.kt                      # Main App Entrypoint & Navigation Router
├── data/
│   ├── Entities.kt                     # Room Database Data Models & Entities
│   ├── MessDao.kt                      # Data Access Objects (DAO) for local DB
│   ├── MessDatabase.kt                 # Room Database Instance & Initial Seed Data
│   ├── MessRepository.kt               # Local Repository Manager
│   └── MessFirestoreRepository.kt      # Cloud Firestore Sync Repository
├── ui/
│   ├── auth/                           # Authentication Logic & Credential Manager
│   ├── components/                     # Reusable Compose Components (NavBars, Banners, Cards)
│   ├── screens/                        # Role-based App Screens
│   │   ├── Page1LoginScreen.kt         # Login & Sign-Up Screen
│   │   ├── StudentDashboardScreens.kt  # Student Home, Weekly Menu, Ledger Screens
│   │   ├── StudentSupportAndNotifScreens.kt # Support Desk & Notifications Screens
│   │   ├── AdminScreens.kt             # Resolution Desk, Billing, Menu Editor, Analytics
│   │   └── StaffScreens.kt             # Guest Passes & Leftover Log Screens
│   └── theme/                          # Color Palettes, Typography, and App Themes
└── viewmodel/
    └── MessViewModel.kt                # Central StateFlow ViewModel & Business Logic
```

---

## 🚀 Getting Started

### Prerequisites
* **Android Studio**: Ladybug / 2024.2+ or Android Studio Jellyfish / Koala.
* **JDK**: Java 11 or Java 17.
* **Android SDK**: Min SDK 24 (Android 7.0), Target SDK 36.

### Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/smart-mess.git
   cd smart-mess
   ```

2. **Open in Android Studio**:
   - Select **File > Open** and choose the `smart-mess` root folder.
   - Allow Gradle sync to download dependencies automatically.

3. **Configure Environment File**:
   - Create a `.env` file in the root directory based on `.env.example`:
     ```env
     GEMINI_API_KEY=your_optional_gemini_api_key
     ```

4. **Build & Run**:
   - Connect an Android physical device or start an Emulator.
   - Press **Run 'app'** (`Shift + F10`).

---

## 📦 Building APK / Deployment

### Build Release APK Locally
To build a standalone APK for testing or direct distribution:
```bash
./gradlew :app:assembleRelease
```
The APK will be generated at:
`app/build/outputs/apk/release/app-release.apk`

### Direct Download via GitHub Releases
You can host APK downloads directly on GitHub:
1. Create a tag/release on GitHub (`v1.0.0`).
2. Attach `app-release.apk` to the Release assets.
3. Share the direct download link:
   `https://github.com/YOUR_USERNAME/smart-mess/releases/download/v1.0.0/app-release.apk`

---

## 🤝 Contributing

Contributions are welcome! Feel free to submit a Pull Request or open an Issue for bug reports and feature enhancements.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
