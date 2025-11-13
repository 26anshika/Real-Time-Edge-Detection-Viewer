# Real-Time-Edge-Detection-Viewer
Real-time Android camera frame processing using OpenCV (C++ via JNI) and OpenGL ES rendering, plus a minimal TypeScript web viewer for edge detection results.


🧾 README.md (Full Draft)
# 📱 Android + OpenCV + OpenGL Assessment (R&D Intern)

This project is a **real-time camera frame processing app** built for the Android + OpenCV-C++ + OpenGL + Web (TypeScript) assessment.  
It demonstrates **JNI integration**, **OpenCV-based edge detection**, **OpenGL texture rendering**, and a **TypeScript-based web viewer** for displaying processed frames.

---

## Overview

**Goal:** Capture live camera frames on Android → process them in native C++ using OpenCV → render the result in real time using OpenGL ES 2.0+.

Additionally, a minimal **TypeScript web viewer** is provided that displays a static processed image (or base64) to simulate bridging native output to a web interface.

---

##  Features Implemented

###  Android (Java/Kotlin + NDK)
-  **Camera Feed Integration** using `Camera2` API and `TextureView`
-  **Frame Processing via JNI** — frames sent to native C++ for processing
-  **OpenCV (C++) Integration** — Canny Edge Detection / Grayscale filter
-  **OpenGL ES 2.0 Rendering** — processed frame displayed as a texture
-  Modular code structure:


/app → Java/Kotlin Android code
/jni → Native C++ code (OpenCV logic)
/gl → OpenGL renderer classes
/web → TypeScript web viewer


### Web (TypeScript)
-  Displays static processed frame (JPEG/Base64)
-  Simple UI with FPS / resolution text overlay
-  Built using plain TypeScript + HTML (compiled via `tsc`)

---

##  Architecture Summary

| Layer | Technology | Responsibility |
|--------|-------------|----------------|
| **Camera Feed (Java/Kotlin)** | Android SDK | Captures live frames via Camera2 API |
| **Native Processing (C++)** | OpenCV + JNI | Applies edge detection or grayscale filter |
| **Rendering (OpenGL)** | OpenGL ES 2.0 | Displays processed texture at 10–15+ FPS |
| **Web Viewer** | TypeScript + HTML | Shows a sample processed frame and basic info |

### 🔗 Frame Flow



Camera (Java) → JNI → C++ (OpenCV) → OpenGL Texture → Display
↓
Export Sample Frame
↓
Web Viewer (TypeScript)


---

## ⚙️ Setup Instructions

###  Prerequisites
- Android Studio (latest)
- Android SDK + NDK
- OpenCV for Android SDK
- Node.js + TypeScript (for web viewer)

###  Android Build Setup


Open in Android Studio

Configure NDK and CMake in local.properties

ndk.dir=<path-to-ndk>
sdk.dir=<path-to-sdk>


Sync Gradle and build the project.

Run on a physical Android device (for camera support).

📸 Screenshots / Demo
Android Edge Detection	Web Viewer

	
(Add screenshots/GIFs after your successful test.)


 Project Structure
edge-viewer/
  ├─ app/                       # Android app module
  │   ├─ src/main/java/...      # MainActivity.kt, renderer
  │   ├─ src/main/cpp/          # native-lib.cpp, CMakeLists.txt
  │   └─ build.gradle
  ├─ gl/                        # (optional separation) GLSurface renderer classes
  ├─ web/
  │   ├─ index.html
  │   ├─ src/viewer.ts
  │   └─ sample.jpg
  ├─ settings.gradle
  └─ gradle/ gradlew files...


👤 Author
Anshika Yadav
📧 2k22.csai.2211504@gmail.com
🌐 [https://github.com/26anshika]

