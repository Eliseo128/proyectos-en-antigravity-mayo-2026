# NavaClinica Admin App Implementation Plan

Building a cross-platform (Android, Web, Windows) Flutter application for dental clinic management.

## User Review Required

> [!IMPORTANT]
> **Firebase Configuration**: I will initialize the code for Firebase, but you will need to provide the `google-services.json` (Android), `GoogleService-Info.plist` (iOS/Mac - not requested but good to keep in mind), and the web configuration keys if you want to run it immediately with your own project. I will use a generic initialization structure.

> [!NOTE]
> **Admin Credentials**: The login will be hardcoded to check for an "admin" role in Firestore after authentication, or simply provide an admin login flow.

## Proposed Changes

### 1. Dependencies & Configuration
Add necessary packages to `pubspec.yaml`:
- `firebase_core`, `firebase_auth`, `cloud_firestore`
- `provider` (State Management)
- `google_fonts` (Typography)
- `animations` (Smooth transitions)
- `font_awesome_flutter` (Icons)

### 2. Architecture (lib/)
Organize the project into a clean architecture:
- `models/`: Data classes (e.g., `Doctor`)
- `services/`: Firebase Auth and Firestore logic
- `screens/`: UI pages (Login, Dashboard, Doctor List/Form)
- `widgets/`: Reusable components (Sidebars, Custom Buttons, TextFields)
- `theme/`: App color schemes and text styles

### 3. Implementation Steps

#### [NEW] [doctor_model.dart](file:///c:/antigravityproyecto/navaclinica/lib/models/doctor_model.dart)
Define the `Doctor` class with fields: id, name, specialty, phone, email, and availability.

#### [NEW] [auth_service.dart](file:///c:/antigravityproyecto/navaclinica/lib/services/auth_service.dart)
Handle Firebase Authentication login/logout.

#### [NEW] [firestore_service.dart](file:///c:/antigravityproyecto/navaclinica/lib/services/firestore_service.dart)
Handle CRUD operations for Doctors.

#### [NEW] [app_theme.dart](file:///c:/antigravityproyecto/navaclinica/lib/theme/app_theme.dart)
Create a premium design system with a deep teal/mint palette, glassmorphism effects for web/windows, and smooth animations.

#### [MODIFY] [main.dart](file:///c:/antigravityproyecto/navaclinica/lib/main.dart)
Setup Firebase initialization and routing.

#### [NEW] [login_screen.dart](file:///c:/antigravityproyecto/navaclinica/lib/screens/login_screen.dart)
Modern login page with background gradients.

#### [NEW] [dashboard_layout.dart](file:///c:/antigravityproyecto/navaclinica/lib/screens/dashboard_layout.dart)
A responsive scaffold with a sidebar for Desktop/Web and a drawer for Mobile.

#### [NEW] [doctor_list_screen.dart](file:///c:/antigravityproyecto/navaclinica/lib/screens/doctors/doctor_list_screen.dart)
List view with search and "Add Doctor" functionality.

## Verification Plan

### Automated Tests
- Run `flutter analyze` to ensure code quality.

### Manual Verification
- Test responsive layout by resizing the window (Web/Windows).
- Verify login flow with Firebase.
- Perform CRUD operations on Doctors and verify in Firestore.
