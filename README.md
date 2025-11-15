# 🧪 Flam-Assessment — Android + OpenCV + C++ + OpenGL ES + Web Viewer

> **Real-Time Edge Detection System** combining Android camera processing, native OpenCV (C++), OpenGL ES rendering, and a complementary TypeScript Web Viewer.

---

## 🚀 Project Summary

**EdgeViewer** is a hybrid Android + Native + Web implementation designed for real-time image processing.  
It integrates:

- 📸 **Camera2 API** for high-speed frame capture  
- 🧠 **C++ + OpenCV (via JNI)** for edge detection  
- 🎨 **OpenGL ES 2.0** for GPU-accelerated preview rendering  
- 🔄 **Mode toggling** between Raw and Edge outputs  
- 🌐 **TypeScript Web Viewer** for desktop visualization or mock testing  

The project demonstrates end-to-end graphics and image-processing architecture—ideal for R&D and performance-critical applications.

---

## ✨ Feature Breakdown

### 🔧 Android (Kotlin)
- High-performance **Camera2** live feed  
- Seamless **JNI bridge** between Kotlin and C++  
- OpenCV-powered **edge detection pipeline**  
- **OpenGL ES renderer** displaying textures in real time  
- Single-tap **Raw ↔ Edge** view switching  
- Built-in **FPS counter**

### 🌐 Web Viewer (TypeScript)
- Canvas-based **frame renderer**  
- Three modes: *Raw*, *Edge*, *Gray*  
- Demo controls: **Play / Pause / Reset**  
- Adjustable **FPS (1–30 FPS)**  
- **Stats panel** (FPS, resolution, frame count, processing time)  
- Ready for **WebSocket streaming**  

---

## 🧩 System Architecture

Android Camera (Camera2)
│ YUV ByteArray
▼
JNI Bridge (Kotlin ↔ C++)
│
▼
Native Layer (C++ / OpenCV)

Edge detection

Frame conversion
│ Texture ID
▼
OpenGL ES Renderer (GLSurfaceView)
│
▼
Real-Time Output on Device

---

## 🛠 Technology Stack

### **Android**
- Kotlin (Gradle + Kotlin DSL)
- NDK / CMake / LLDB
- Camera2 API
- JNI communication
- OpenGL ES 2.0 rendering

### **Native (C++)**
- OpenCV (image processing)
- GLES2 pipeline
- JNI native methods

### **Frontend Web**
- TypeScript 5.3
- ES2020 Modules
- HTML5 Canvas
- WebSocket API
- http-server (Node)

---

## 📁 Repository Structure
```
edgedetector2/
├── app/ # Android module (Kotlin)
│ ├── src/main/
│ │ ├── AndroidManifest.xml
│ │ ├── java/com/example/edgeviewer/
│ │ │ ├── MainActivity.kt
│ │ │ ├── CameraController.kt
│ │ │ ├── GLTextureRenderer.kt
│ │ │ └── Utils.kt
│ │ └── res/
│ │ ├── layout/activity_main.xml
│ │ └── values/strings.xml
│ ├── build.gradle
│ └── CMakeLists.txt
│
├── jni/ # Native C++ (OpenCV + GLES)
│ ├── native-lib.cpp
│ ├── ImageProcessor.cpp
│ ├── ImageProcessor.h
│ └── CMakeLists.txt
│
├── gl/ # GLSL shader files
│ ├── vertex.glsl
│ └── fragment.glsl
│
├── opencv/ # OpenCV Android SDK
│
├── web/ # Web Viewer (TypeScript)
│ ├── src/
│ │ ├── app.ts
│ │ ├── frameRenderer.ts
│ │ ├── statsDisplay.ts
│ │ ├── websocketClient.ts
│ │ ├── types.ts
│ │ └── demoData.ts
│ ├── index.html
│ ├── styles.css
│ ├── package.json
│ ├── tsconfig.json
│ 
│
├── README.md
├── .gitignore
```
---

## 📦 Setup & Installation

### 1️⃣ Clone the Project

```bash
git clone https://github.com/UDAY1810/edgedetector2
cd edgedetector2

⚙ Android Configuration
2️⃣ Install OpenCV Android SDK

Download OpenCV-android-sdk.zip → extract → place here:
Edge-detection/opencv/
└── sdk/native/
    ├── jni/
    ├── libs/
    └── include/
3️⃣ Enable NDK Tools

In Android Studio:
File → Settings → SDK Manager → SDK Tools
4️⃣ Configure CMakeLists.txt (Native)

Add to jni/CMakeLists.txt:
set(OpenCV_DIR ${CMAKE_SOURCE_DIR}/../opencv/sdk/native/jni)
find_package(OpenCV REQUIRED)

target_link_libraries(
    edge_native
    ${OpenCV_LIBS}
    log
    GLESv2
)
5️⃣ Configure app/build.gradle
externalNativeBuild {
    cmake {
        path "../jni/CMakeLists.txt"
        version "3.10.2"
    }
}
6️⃣ Launch App on Device

Turn on Developer Options

Enable USB Debugging

Connect device

Select your device

Hit Run ▶

Once running:

Camera preview starts immediately

Edge mode toggle is active

FPS counter updates in real time

🌐 Web Viewer Setup
Navigate to web directory
cd web

Install dependencies:

npm install


Build TypeScript:

npm run build


Start local server:

npm run serve


Open in browser:

http://localhost:8081

🔗 Repository 

GitHub: https://github.com/UDAY1810/edgedetector2
