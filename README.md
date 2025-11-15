🧠 Real Time Edge Detection
A real-time hybrid Android + Native (C++ + OpenCV + OpenGL) application for edge detection and GPU-accelerated rendering, with a companion *TypeScript Web Viewer demo.

🚀 Overview
EdgeViewer captures live camera frames using Android’s Camera2 API, processes them natively through *OpenCV via JNI, and renders them using *OpenGL ES 2.0 for smooth, real-time visualization.
It also includes a lightweight TypeScript Web Viewer for static or mock data visualization.

✨ Features
Feature	Description
📸 Camera2 Live Preview	High-performance real-time camera feed
⚙ Native C++ + OpenCV Integration	Edge detection implemented using OpenCV through JNI
🎨 OpenGL ES Renderer	GPU-accelerated rendering pipeline for visual output
🔁 Toggle Modes	Switch between Raw and Edge-Detected frames instantly
⏱ FPS Counter	Displays live frames-per-second performance
🌐 TypeScript Web Viewer	Simple front-end to display frames or mock data
🏗 Architecture
EdgeViewer
├─ app/
│ ├─ src/main/
│ │ ├─ AndroidManifest.xml
│ │ ├─ java/com/example/edgeviewer/
│ │ │ ├─ MainActivity.kt
│ │ │ ├─ CameraController.kt
│ │ │ ├─ GLTextureRenderer.kt
│ │ │ └─ Utils.kt
│ │ └─ res/
│ │ ├─ layout/activity_main.xml
│ │ └─ values/strings.xml
│ ├─ build.gradle
│ └─ CMakeLists.txt
├─ jni/
│ ├─ native-lib.cpp
│ ├─ ImageProcessor.cpp
│ ├─ ImageProcessor.h
│ └─ CMakeLists.txt
├─ gl/
│ └─ shaders/
│ ├─ vertex.glsl
│ └─ fragment.glsl
├─ opencv/
├─ README.md
├─ .gitignore
└─ LICENSE
⚙ Setup & Installation
🔹 Android Setup
Open the project in Android Studio
Ensure NDK and CMake are installed:
Android Studio → SDK Tools → NDK & CMake

Sync Gradle to resolve dependencies
Integrate OpenCV SDK
Download the OpenCV Android SDK

Copy libraries to:
bash app/src/main/jniLibs/

Update your CMakeLists.txt to link opencv_java4

Build & Run
Connect a physical Android device
Click ▶ Run in Android Studio
Grant Camera permissions when prompted
--

🎥 ScreenShots !
WhatsApp Image 2025-11-13 at 23 27 02_788e9ec0 WhatsApp Image 2025-11-13 at 23 26 51_c8337be4 WhatsApp Image 2025-11-13 at 23 30 30_84bb1e6c WhatsApp Image 2025-11-13 at 23 32 12_95de9846 WhatsApp Image 2025-11-13 at 23 34 01_e7ff44fb

🛠 Tech Stack
Android (Frontend)
Kotlin
Camera2 API for high-performance frame capture
OpenGL ES 2.0 for GPU-based rendering
Native (Backend)
C++ via JNI
OpenCV for image processing and edge detection
Native bridge integration between Kotlin and C++
Web Viewer
TypeScript
HTML/CSS for lightweight visualization
📂 Folder Summary
Folder	Description
app/	Android application source (Kotlin + XML layouts)
jni/	Native C++ source and OpenCV processing logic
gl/	GLSL shaders for OpenGL rendering
opencv/	OpenCV SDK integration
web/	TypeScript demo viewer
🧩 Key Learning
Hands-on with *Camera2 API, **NDK, and *CMake
Real-time OpenCV processing using JNI
GPU-accelerated visualization via OpenGL ES
Bridging between Android Kotlin layer and Native C++ layer