🚀 Real-Time Edge Detection Viewer
Android + OpenCV (C++) + OpenGL ES + Web (TypeScript)

This project is an end-to-end implementation of a real-time camera frame processing pipeline using:

Android (Kotlin)

OpenCV (C++ via NDK / JNI)

OpenGL ES 2.0 for rendering

TypeScript Web Viewer

The app captures live camera frames, sends them to native C++ code, performs Canny Edge Detection, and displays the output using OpenGL ES.
A companion web viewer displays a sample processed frame using TypeScript.

🧩 Features Implemented
✅ Android Application
✔ Real-Time Camera Feed

Implemented using Camera2 API with TextureView.

✔ Native (C++) Frame Processing

Frames passed via JNI to native code.

OpenCV C++ implementation of:

Canny Edge Detection

Grayscale conversion

Efficient memory reuse to maintain > 15 FPS.

✔ OpenGL ES Rendering

Processed frames mapped to a texture.

Rendered with OpenGL ES 2.0 using a quad shader pipeline.

Smooth real-time display.

✔ Optional UI Features

Button toggle for Raw / Edge-detected modes.

FPS counter.

🌐 Web Viewer (TypeScript)

A minimal TypeScript project that:

Loads and displays a processed sample frame (sample_output.png or base64).

Shows FPS and resolution text overlay.

Demonstrates DOM updates & modular TypeScript structure.

📁 Project Structure
root/
│── app/
│   ├── src/main/java/...     # Kotlin camera + JNI + GL code
│   ├── src/main/cpp/         # Native C++ (OpenCV + processing)
│   └── src/main/assets/      # Shaders (vertex/fragment)
│
│── gl/                       # OpenGL renderer classes
│   ├── GLRenderer.kt
│   ├── GLUtils.kt
│   └── shaders/
│
│── jni/                      # C++ source (NDK)
│   ├── CMakeLists.txt
│   ├── native-lib.cpp
│   └── image_processing.cpp
│
│── web/
│   ├── index.html
│   ├── src/app.ts
│   ├── dist/
│   └── tsconfig.json
│
└── README.md

⚙️ How the System Works
🔁 1. Frame Capture

Kotlin captures frames via ImageReader or TextureView.

Camera → SurfaceTexture → ByteArray (YUV)

🔀 2. JNI Transfer

Frame (RGBA) is passed to C++:

nativeProcessFrame(inputArray, width, height)

⚙️ 3. OpenCV Processing (C++)

Inside native-lib.cpp or image_processing.cpp:

Convert RGBA → Grayscale

Apply Canny

Return processed buffer

cvtColor(src, gray, COLOR_RGBA2GRAY);
Canny(gray, edges, 80, 150);

🎨 4. OpenGL Rendering

Output image set as a texture:

C++ processed frame → GPU texture → Render quad → Display

🌍 5. Web Viewer

Static sample frame loaded through TypeScript:

const img = document.getElementById("preview") as HTMLImageElement;
img.src = "sample_output.png";

🧰 Setup Instructions
✅ 1. Install Requirements
Android:

Android Studio Ladybug+

SDK 34+

NDK 26.x

CMake 3.22+

OpenCV Android SDK

Web:

Node.js + npm

TypeScript (npm install -g typescript)

✅ 2. Configure OpenCV in Android

Download OpenCV Android SDK.

Put inside:

app/src/main/cpp/opencv/


Modify CMakeLists.txt:

include_directories(${OpenCV_DIR}/sdk/native/jni/include)
add_library(opencv_java4 SHARED IMPORTED)
set_target_properties(opencv_java4 PROPERTIES IMPORTED_LOCATION
${OpenCV_DIR}/sdk/native/libs/${ANDROID_ABI}/libopencv_java4.so)

✅ 3. Build & Run Android App
Open Android Studio → Build → Run


Ensure your device supports Camera2 + OpenGL ES 2.0.

✅ 4. Build & Run Web Viewer
cd web
npm install
tsc
open index.html in browser

🧠 Architecture Summary
Kotlin Layer

Camera setup + buffer handling

OpenGL surface management

JNI bridge calls

C++ Layer

Zero-copy buffer processing

OpenCV image pipeline

Frame returned to Kotlin

OpenGL Layer

Compiles shaders

Uploads textures

Renders output on GLSurfaceView

Web Layer (TypeScript)

Minimal viewer for processed image

DOM updates + modular TS

🧪 Tech Stack
Layer	Tech
Android	Kotlin, Camera2, TextureView
Native	C++, OpenCV 4.x, NDK
Rendering	OpenGL ES 2.0, GLSL
Communication	JNI
Web	TypeScript, HTML, CSS