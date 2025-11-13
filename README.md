🧠 Real-Time Edge Detection
Software Engineering Intern (R&D) — Adobe (Assessment Project)

A real-time hybrid Android + Native (C++ + OpenCV + OpenGL ES) application for GPU-accelerated edge detection, along with a lightweight TypeScript Web Viewer for demo visualization.

This project demonstrates skills in low-level camera handling, native image processing, OpenGL rendering, and web integration.

🚀 Overview

EdgeViewer captures live camera frames using Android’s Camera2 API, processes them with OpenCV (C++) via JNI, and renders the output using OpenGL ES 2.0, achieving a smooth and responsive visualization pipeline.

A companion TypeScript Web Viewer displays static or mock processed frames.

✨ Features
Feature	Description
📸 Camera2 Live Preview	High-performance real-time camera feed
⚙ Native C++ + OpenCV Integration	Canny Edge Detection implemented in OpenCV via JNI
🎨 OpenGL ES Renderer	GPU-accelerated rendering pipeline
🔁 Toggle Modes	Switch between Raw and Edge-Detected frames instantly
⏱ FPS Counter	Live frames-per-second performance display
🌐 TypeScript Web Viewer	Simple front-end for mock/static visualization
🏗 Architecture
EdgeViewer
├─ app/
│  ├─ src/main/
│  │  ├─ AndroidManifest.xml
│  │  ├─ java/com/example/edgeviewer/
│  │  │  ├─ MainActivity.kt
│  │  │  ├─ CameraController.kt
│  │  │  ├─ GLTextureRenderer.kt
│  │  │  └─ Utils.kt
│  │  └─ res/
│  │     ├─ layout/activity_main.xml
│  │     └─ values/strings.xml
│  ├─ build.gradle
│  └─ CMakeLists.txt
│
├─ jni/
│  ├─ native-lib.cpp
│  ├─ ImageProcessor.cpp
│  ├─ ImageProcessor.h
│  └─ CMakeLists.txt
│
├─ gl/
│  └─ shaders/
│      ├─ vertex.glsl
│      └─ fragment.glsl
│
├─ opencv/                # OpenCV SDK integration
├─ web/                   # TypeScript Web Viewer
├─ README.md
└─ .gitignore

⚙ Setup & Installation
🔹 Android Setup
1️⃣ Open the project in Android Studio

Make sure NDK and CMake are installed:

Android Studio → SDK Tools → NDK, CMake

2️⃣ Sync Gradle

Android Studio will automatically configure your build files.

3️⃣ Integrate OpenCV SDK

Download the OpenCV Android SDK and copy the native libraries to:

app/src/main/jniLibs/


Update your CMakeLists.txt to link:

opencv_java4

4️⃣ Build & Run

Connect a physical Android device

Click ▶ Run in Android Studio

Grant Camera permissions

🎥 Screenshots

(Add actual images from your device here)
Example format:

/screenshots/shot1.jpg  
/screenshots/shot2.jpg  
/screenshots/shot3.jpg  
/screenshots/shot4.jpg  
/screenshots/shot5.jpg  

🛠 Tech Stack
Android (Frontend)

Kotlin

Camera2 API

OpenGL ES 2.0 (GPU-based rendering)

Native (Backend)

C++

JNI bridge

OpenCV (Canny, Grayscale, image transforms)

Web Viewer

TypeScript

HTML / CSS

📂 Folder Summary
Folder	Description
app/	Android app (Kotlin + XML layouts)
jni/	Native C++ OpenCV processing
gl/	GLSL shaders + rendering utilities
opencv/	Imported OpenCV SDK
web/	TypeScript mock viewer
screenshots/	App screenshots (add your images)
🧩 Key Learnings

Practical experience with Camera2 API

NDK, JNI, and CMake integration

Real-time OpenCV C++ processing

OpenGL ES rendering pipeline

Architecture design across Kotlin → JNI → C++ → GPU

Simple TypeScript visualization frontend
