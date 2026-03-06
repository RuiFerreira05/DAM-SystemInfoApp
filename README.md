# Assignment TP1 — System Info App
Course: Desenvolvimento de Aplicações Móveis (DAM)
Student(s): Rui Ferreira (a51597)
Date: March 6th, 2026
Repository URL: https://github.com/RuiFerreira05/DAM-SystemInfoApp.git
---
## 1. Introduction
The "System Info App" is an Android mini-project designed to explore device capabilities and system properties. Developed as part of Tutorial 1, this application fetches and displays fundamental hardware and software specifications of the host Android device, offering an introductory look into interacting with the Android framework APIs.

## 2. System Overview
The application consists of a single screen featuring a `MultiLine Text` widget (an `EditText` widget configured for multiline read-only display). Upon launching, the application immediately reads various properties from the `android.os.Build` object and populates the text field, giving the user a clean, text-based overview of their device's build configuration.

## 3. Architecture and Design
This is a straightforward, single-activity Android application built entirely natively using Kotlin and XML:
- **`MainActivity.kt`**: Contains the core logic for retrieving device information and updating the UI. Edge-to-edge display is explicitly configured, showing the utilization of window insets.
- **`activity_main.xml`** (Layout): Uses standard View framework layouts to hold the `EditText` (multiline) for displaying properties.

## 4. Implementation
The main functionality lies in accessing the `android.os.Build` object to gather system properties dynamically stringing them into a unified block of text:
- **Property Extraction**: `MANUFACTURER`, `MODEL`, `BRAND`, `TYPE`, `USER`, `VERSION_CODES.BASE`, `VERSION.INCREMENTAL`, `VERSION.SDK_INT`, `VERSION.RELEASE`, and `DISPLAY`.
- **UI Binding**: `buildString` is used for efficient string concatenation. Once formatted, `setText` dictates the contents of the `EditText` (`R.id.MultiLineText`).
- **Edge-to-Edge Padding**: `WindowInsetsCompat` manages system bar padding securely inside the `onCreate` method.

## 5. Testing and Validation
The application can be validated by running it on various Android Virtual Devices (AVDs) or physical devices.
- **Test Scenarios**: Launching the app on different API levels (e.g., API 34 vs API 29) to ensure that properties resolve correctly natively and appropriately. 
- **Validation**: Verifying that the multiline text box successfully inflates and doesn't get occluded by notches or system navigation bars, thanks to the insets listener.

## 6. Usage Instructions
1. Clone the repository: `git clone https://github.com/RuiFerreira05/DAM-SystemInfoApp.git`
2. Open the project in Android Studio (Panda 1 or newer recommended).
3. Wait for the Gradle project sync.
4. Execute via **Run** (`Shift + F10`) targeting either an emulator or a connected physical unit via USB Debugging.
5. Review the on-screen device properties displayed directly within the app.

---
# Development Process
## 12. Version Control and Commit History
Git was used throughout the development cycle. Initially contained within a larger monorepo structure alongside the other Tutorial 1 assignments, it was eventually separated into its own standalone repository to maintain modularity.

## 13. Difficulties and Lessons Learned
- **Framework API Integration**: Gaining familiarity with the `android.os.Build` class documentation to discover which variables expose meaningful information. 
- **Edge-to-Edge Adjustments**: Adapting UI layouts to system bar insets correctly so the text is fully readable and doesn't collide with the transparent status bar.

## 14. Future Improvements
- Style the UI further to use a `RecyclerView` with clear key-value pairs instead of a single raw text blob.
- Incorporate other system APIs such as the `TelephonyManager` or `BatteryManager` to extend the scope of the app's diagnostic features.
---
## 15. AI Usage Disclosure (Mandatory)
No AI tools were explicitly used to compose the code sequence of this component as it fell under the "[AC NO, AI NO]" guidelines constraint.
