## Note: This repository serves as a technical showcase and architectural overview. The actual iOS source code is kept in a private repository to protect proprietary game logic.

# Nod 'n' Drift 🏍️🎧

An iOS 3D arcade racer steered entirely by your head movements using AirPods spatial audio sensors. 

<img width="250" alt="IMG_0906" src="https://github.com/user-attachments/assets/311d9b69-1152-439d-ab18-eaf661ccf204" />

 
## 📖 Overview
Nod 'n' Drift is a motion-controlled survival racer that bridges hardware sensors with 3D rendering. Instead of touching the screen, players physically tilt their heads left and right to steer, nod down to trigger a speed boost, and tilt their chin up to hit the brakes. 

## ✨ Key Features
* **Low-Latency Head Tracking:** Parses real-time pitch, roll, and yaw data directly from AirPods using `CMHeadphoneMotionManager`.
* **Modern, Clean UI:** Features custom, programmatic `UIVisualEffectView` frosted-glass overlays for menus and states (Pause, Game Over, Settings, AirPods Disconnect) that integrate seamlessly without interrupting the 3D render loop.
* **Deep iOS Integration:** Includes a custom, polished Launch Screen and a dynamic App Icon designed to flawlessly adapt to Apple's Light, Dark, and Tinted home screen system preferences.
* **Procedural 3D World:** Endless, performant generation of roads, traffic, and scenery using node-recycling and memory caching to maintain a flawless 60FPS.
* **Thread-Safe Architecture:** Utilizes `NSLock` to prevent data races between the background CoreMotion sensor thread and the main SceneKit render loop.
* **Dynamic Audio:** Engine RPM audio pitches up and down dynamically based on the physics engine's current velocity.

## 📸 Interface Showcase

<img width="1160" height="447" alt="Screenshot" src="https://github.com/user-attachments/assets/2714c440-803a-4771-9329-409cd259f6da" />
 
*Dynamic App Icon adapting to iOS Light and Dark modes.*


<img width="250" alt="IMG_0916" src="https://github.com/user-attachments/assets/ba74b40f-d0cc-406f-805a-a9d0dce3f4b2" />
 
*Premium main menu featuring dynamic AirPods connection status and Game Center integration.*


<img width="250" alt="IMG_0917" src="https://github.com/user-attachments/assets/5c44b932-4017-4a5d-bad1-24e3ff3f9ea1" />
 
*Crash overlay with local best score tracking and hardware gesture hints.*


<img width="250" alt="IMG_0918" src="https://github.com/user-attachments/assets/3f13cd96-b1be-4980-b024-95721c119073" />
 
*Clean settings panel with live hardware tracking, custom control toggles, and comprehensive device compatibility guides.*


### State Management & Error Handling
Handling hardware disconnections gracefully is critical for a seamless experience. If the user's AirPods disconnect, or if they try to play without them, the game immediately halts the 3D render loop and presents a clean prompt to guide them back.

<img width="250" alt="IMG_0920" src="https://github.com/user-attachments/assets/166b4903-d578-4c2a-acf3-a21cff596efd" />


## 🛠️ Tech Stack
* **Swift 5** 
* **SceneKit** (3D Rendering & Physics)
* **CoreMotion** (Hardware Spatial Audio Tracking)
* **GameKit** (Apple Leaderboards)
* **AVFoundation** (Audio processing on `.userInteractive` global queues)

## 🚀 How to Run Locally
1. Clone this repository to your Mac.
2. Open `Nod 'n' Drift.xcodeproj` in Xcode.
3. Connect your iPhone via cable (headphone motion tracking requires a physical device and cannot be tested on the Xcode Simulator).
4. Select your iPhone as the run destination and hit `Cmd + R`.
5. Connect compatible AirPods (AirPods Pro, AirPods Max, or AirPods 3rd/4th Gen) to your iPhone and start drifting. 

## 📋 Requirements
- iPhone running iOS 14.0+
- AirPods Pro, AirPods Max, or AirPods (3rd/4th Gen)
- Xcode 14+
- Physical device required (Simulator not supported)

---
*Developed by Hemanth*
