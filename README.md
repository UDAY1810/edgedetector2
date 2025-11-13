# 🧠 Real Time Edge Detection 

A real-time hybrid **Android + Native (C++ + OpenCV + OpenGL)** application for GPU-accelerated edge detection, with a companion **TypeScript Web Viewer** demo.

---

## 🚀 Overview

**EdgeViewer** captures live camera frames using Android’s **Camera2 API**, processes them natively through **OpenCV (C++ via JNI)**, and renders the output using **OpenGL ES 2.0** for smooth real-time visualization.  
It includes a lightweight **TypeScript Web Viewer** for static or mock data display.

---

## ✨ Features

| Feature | Description |
|--------|-------------|
| 📸 **Camera2 Live Preview** | High-performance real-time camera feed |
| ⚙️ **Native C++ + OpenCV Integration** | Edge detection implemented using OpenCV through JNI |
| 🎨 **OpenGL ES Renderer** | GPU-accelerated rendering pipeline for visual output |
| 🔁 **Toggle Modes** | Instantly switch between *Raw* and *Edge-Detected* frames |
| ⏱ **FPS Counter** | Displays real-time frames-per-second |
| 🌐 **TypeScript Web Viewer** | Simple front-end to display frames or mock processed data |

---

## 🏗 Architecture

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
│
├─ jni/
│ ├─ native-lib.cpp
│ ├─ ImageProcessor.cpp
│ ├─ ImageProcessor.h
│ └─ CMakeLists.txt
│
├─ gl/
│ └─ shaders/
│ ├─ vertex.glsl
│ └─ fragment.glsl
│
├─ opencv/
├─ web/
├─ README.md
└─ .gitignore


---

## ⚙️ Setup & Installation

### 🔹 Android Setup

1. **Open the project** in Android Studio  
2. Ensure **NDK** and **CMake** are installed:  


Android Studio → SDK Tools → NDK, CMake

3. **Sync Gradle** to resolve all dependencies  
4. **Integrate OpenCV SDK**  
- Copy OpenCV native libs to:  
  ```
  app/src/main/jniLibs/
  ```
- Link `opencv_java4` inside your CMakeLists  
5. **Build & Run**  
- Connect a physical device  
- Tap **Run (▶)**  
- Grant camera permission  


---

## 🛠 Tech Stack

### **Android (Frontend)**
- Kotlin  
- Camera2 API  
- OpenGL ES 2.0  

### **Native (Backend)**
- C++  
- JNI  
- OpenCV  

### **Web Viewer**
- TypeScript  
- HTML/CSS  

---

## 📂 Folder Summary

| Folder | Description |
|--------|-------------|
| `app/` | Android source (Kotlin + XML layouts) |
| `jni/` | Native C++ OpenCV processing |
| `gl/` | GLSL shader programs |
| `opencv/` | OpenCV SDK integration |
| `web/` | TypeScript viewer |
| `screenshots/` | App screenshots |

---

## 🧩 Key Learning

- Deep understanding of **Camera2 API**, **NDK**, **JNI**, and **CMake**  
- Real-time image processing using **OpenCV (C++)**  
- GPU-accelerated visualization via **OpenGL ES**  
- Smooth pipeline between **Kotlin → JNI → C++ → GPU**  
- Lightweight web-based visualization in **TypeScript**  

---



