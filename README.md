# 🛒 Swag Labs Mobile Automation (Maestro)

[![Maestro](https://img.shields.io/badge/Tested%20with-Maestro-purple)](https://maestro.mobile.dev/)
[![Platform](https://img.shields.io/badge/Platform-Android-green)](https://www.android.com/)
[![Status](https://img.shields.io/badge/Status-Passing-success)]()

## 📄 Overview

This project is an end-to-end (E2E) mobile automation framework built using **Maestro**. It automates the critical user flows of the **Swag Labs (Sauce Demo)** Android application, covering the entire journey from login to order completion and logout.

The goal of this project is to demonstrate robust UI testing capabilities, handling complex scenarios like keyboard management, scrolling, and dynamic element identification without relying on brittle locators.

## 🚀 Features Automating

The script `SwagLabsTest.yaml` covers the following "Happy Path" scenario:

1.  **Authentication:**
    * Valid Login with `standard_user`.
    * Handling keyboard visibility to access hidden buttons.
2.  **Inventory Management:**
    * Browsing the product list.
    * Adding an item to the cart.
3.  **Cart & Checkout:**
    * Navigating to the cart using ID/coordinate fallback.
    * Proceeding to checkout.
    * Entering shipping details (First Name, Last Name, Zip).
4.  **Order Completion:**
    * Dynamic scrolling to find the "Finish" button.
    * Verifying order success message.
5.  **Logout Flow:**
    * Accessing the side menu (Hamburger menu).
    * Successfully logging out to the login screen.

## 🛠 Tech Stack

* **Framework:** [Maestro](https://maestro.mobile.dev/) (YAML-based automation)
* **Platform:** Android (Tested on Genymotion Emulator)
* **App Under Test:** [Sauce Labs Sample App](https://github.com/saucelabs/sample-app-mobile)
* **Tools:** ADB (Android Debug Bridge), Maestro Studio

## 📂 Project Structure

```bash
SwagLabs-Automation/
├── README.md               # Project Documentation
├── SwagLabsTest.yaml       # Main Test Script
└── flows/                  # (Optional) Reusable sub-flows
    ├── login.yaml
    └── checkout.yaml



Prerequisites
Before running the tests, ensure you have the following installed:

Maestro:

Bash

curl -Ls "[https://get.maestro.mobile.dev](https://get.maestro.mobile.dev)" | bash
Android Emulator: (Genymotion or Android Studio)

The App: Install the Swag Labs APK on your emulator.

Package Name: com.swaglabsmobileapp

🏃‍♂️ How to Run
Clone the Repository:

Bash

git clone [https://github.com/YOUR_USERNAME/SwagLabs-Maestro.git](https://github.com/YOUR_USERNAME/SwagLabs-Maestro.git)
cd SwagLabs-Maestro
Launch your Emulator.

Run the Test:

Bash

maestro test SwagLabsTest.yaml
Run with Continuous Mode (Optional):

Great for development. The test re-runs automatically when you save the file.

Bash

maestro test -c SwagLabsTest.yaml
💡 Key Challenges Solved
Ghost Elements: Implemented scrollUntilVisible to handle buttons (like "FINISH") that appear below the fold on smaller screens.

Keyboard Interception: Used hideKeyboard commands to prevent the on-screen keyboard from blocking CTA buttons during checkout.

Element Reliability: Used resource IDs (test-Cart) where available, with coordinate fallbacks for robustness across different device sizes.

📸 Screenshots / Demo
<img width="1306" height="803" alt="Screenshot 2026-01-29 at 11 08 52 AM" src="https://github.com/user-attachments/assets/daad2187-a595-452d-b9f1-de5470fff8c2" />
