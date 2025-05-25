# SecureCrack - CTF Android App (SMD Assignment 3)


**SecureCrack** is a vulnerable Android application intentionally designed for educational purposes. It serves as a Capture The Flag (CTF) challenge, encouraging students to apply reverse engineering and mobile app security techniques.

---

## Overview

**App Name:** SecureCrack  
**Platform:** Android (Java, Android Studio)  
**Purpose:** CTF Challenge for SMD Assignment 3 — Learn and test reverse engineering techniques.

---

## Features

- Login screen with hardcoded credentials.
- Flag displayed only after successful login.
- Vulnerable to reverse engineering (e.g., `jadx`, `apktool`, `Frida`, etc.)
- Obfuscation intentionally omitted to keep it beginner-friendly.

---

## Project Structure

```
SecureCrack/
├── app/
│   ├── java/
│   │   └── com/example/securecrack/
│   │       ├── MainActivity.java
│   │       └── SecretActivity.java
│   └── res/
│       ├── layout/
│       │   ├── activity_main.xml
│       │   └── activity_flag.xml
│       └── values/
│           └── strings.xml
├── AndroidManifest.xml
└── build.gradle
```

---

## How It Works

### MainActivity.java

- Displays a login screen.
- Hardcoded credentials (e.g., `username: admin`, `password: pass1234`).
- On correct login, navigates to `SecretActivity`.

```java
String correctUsername = "admin";
String correctPassword = "pass1234";

if (username.equals(correctUsername) && password.equals(correctPassword)) {
    Intent intent = new Intent(MainActivity.this, SecretActivity.class);
    startActivity(intent);
}
```

---

### SecretActivity.java

- Displays the **FLAG** only if login was successful.

```java
TextView flagText = findViewById(R.id.flagText);
flagText.setText("CTF{Reverse_It_And_You_Shall_Find}");
```

---

##  Reverse Engineering Challenge

### Objective:

> Decompile or reverse the APK to discover the login credentials or extract the flag.

### Tools You Can Use:

- `jadx` or `apktool` – for static analysis.
- `Frida` – for runtime dynamic analysis.
- `adb` – to interact with the app/emulator.
- Android Studio – for code inspection or modification.

---

##  How to Build & Test

### Prerequisites

- Android Studio installed
- Android SDK setup
- Emulator or real Android device

### Build Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/whelmzy05/SecureCrack-CTF
   cd SecureCrack
   ```

2. Open the project in Android Studio.

3. Build and run the app:
   - Either on an emulator or connected Android device.

4. Use the following credentials to log in (or reverse the APK to find them):
   - **Username:** `admin`
   - **Password:** `pass1234`

---

## Flag

Displayed on successful login screen:

```
CTF{Reverse_It_And_You_Shall_Find}
```

---

## License

This project is created for educational and non-commercial purposes only as part of an SMD university assignment.

---
