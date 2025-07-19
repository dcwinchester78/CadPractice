# CadPractice
# 🧩 Basic CAD App – .NET MAUI Blazor Edition

## 📝 Overview

This is a lightweight CAD application built using **.NET MAUI with Blazor**. It runs as a **native desktop application** and renders the UI using **Razor components**. The app supports basic 2D and 3D modeling with just two shape types: **rectangles** and **cylinders**.

The main UI is a **Blazor component hosted inside a MAUI shell window**, combining the power of native desktop with the simplicity of web-style UI components.

---

## 🛠️ Tech Stack

- **Framework**: .NET MAUI with Blazor WebView  
- **Language**: C#  
- **UI**: Razor Components (Blazor) hosted in native MAUI shell  
- **Graphics**: HTML5 Canvas + JavaScript Interop  
- **Platforms**: Windows (primary), macOS (optional)  
- **Tools**: Visual Studio 2022/2023, .NET SDK 8 or 9

---

## 🚀 Project Setup Instructions

### 1. Create the Project
Start by creating a new .NET MAUI Blazor project called `MyCadApp`.

### 2. Add a Blazor Component
Create a `CadCanvas.razor` component that will render a canvas element. This component will be the main entry point of the app's UI.

### 3. Create JavaScript for Canvas
Add a JavaScript file in `wwwroot` that will draw rectangles and cylinders onto the HTML5 canvas. Include this script in your `index.html`.

### 4. Wire Up the Component in MAUI Shell
Update `MainPage.xaml` to host the `CadCanvas.razor` component as the root component in the `BlazorWebView`.

### 5. Run the App
Build and run the app to see the native MAUI window rendering your Blazor component.

---

## 🎯 Features

### ✅ Core Features

- Native MAUI window hosting Blazor UI
- Canvas-based drawing surface using HTML5
- Render rectangles and cylinders
- JavaScript interop for drawing operations
- Toolbar for shape actions
- Shape model in C#
- Load/save project files

### 🧪 Optional Features (Future Work)

- Pan and zoom canvas
- Snap-to-grid functionality
- Shape selection and transformations
- Export to SVG or image formats
- Undo/redo support

---

## 📁 Custom File Format

Project files use a `.mycad` extension and store shape data in JSON format. The file contains basic shape definitions including type, position, and dimensions.

---

## 🧪 Testing Plan

- Manual interaction testing
- File save/load validation
- Model unit tests (shape structure and logic)
- Cross-platform testing on Windows/macOS

---

## 📅 Development Timeline

| Phase             | Deliverable                               | Target Date |
|------------------|--------------------------------------------|-------------|
| Phase 1          | Project setup and canvas display           | Week 1      |
| Phase 2          | Shape rendering and toolbar UI             | Week 2      |
| Phase 3          | File format implementation                 | Week 3      |
| Phase 4          | Interactions and polishing                 | Week 4-5    |

---

## 👥 Team Roles

- **App Architect** – Set up project structure and shell  
- **UI Developer** – Create Razor components and layout  
- **Graphics Dev** – Implement JavaScript drawing logic  
- **Backend Dev** – Build shape model and file logic  
- **QA Tester** – Perform manual testing and report issues

---

## 📌 Summary

This app serves as a minimal CAD prototype using modern .NET technologies. It combines native deployment (via MAUI) with web-based UI (via Blazor) and canvas drawing (via JavaScript). It’s clean, fast to prototype, and cross-platform friendly with a clear separation between UI, drawing, and logic.

---

