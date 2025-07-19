# 🧩 MyCadApp – .NET MAUI Blazor CAD Application

## 📝 Overview

**MyCadApp** is a lightweight CAD application built with **.NET MAUI Blazor**, combining native desktop power with modern Blazor UI. It supports basic 2D/3D modeling with two primitive shapes: **rectangles** and **cylinders**.

The app runs inside a native MAUI shell window and renders its interface using a **Blazor Razor component** hosted in a **BlazorWebView**. It uses an HTML5 `<canvas>` element for rendering and JavaScript interop for drawing.

---

## 🛠️ Tech Stack

- **Framework**: .NET MAUI with Blazor WebView
- **Language**: C#
- **UI**: Razor Components (Blazor) hosted in native MAUI shell
- **Graphics**: HTML5 Canvas + JavaScript Interop
- **Platform Targets**: Windows (primary), macOS (optional)
- **Tools**: Visual Studio 2022/2023, .NET SDK 8 or 9

---

## 🚧 Project Phases & Steps

### 📦 Phase 1: Project Initialization & Shell Setup

**Objective:** Set up the MAUI Blazor project and render a custom Razor component.

- Create a new .NET MAUI Blazor project named `MyCadApp`.
- Confirm default project builds and runs successfully.
- Create a folder named `Components`.
- Add a new Razor component: `CadCanvas.razor`.
- Modify `MainPage.xaml` to host `CadCanvas.razor` in the `BlazorWebView`.

**Outcome:**  
The app opens a native window and displays a blank `CadCanvas` component.

---

### 🎨 Phase 2: Canvas UI & JavaScript Interop

**Objective:** Add a canvas element and integrate JS interop to draw sample shapes.

- Add a `<canvas>` element in `CadCanvas.razor`.
- Inject `IJSRuntime` and call JS in `OnAfterRenderAsync`.
- Create a `cadCanvas.js` file in `wwwroot`.
- Draw a rectangle and an ellipse in JavaScript.
- Link `cadCanvas.js` in `wwwroot/index.html`.

**Outcome:**  
Canvas displays a hardcoded rectangle and cylinder when the app launches.

---

### 🧠 Phase 3: Shape Model & State Management

**Objective:** Store shape data in memory using a shape model and service.

- Create a `CadShape` class with shape type, position, size.
- Implement a singleton `CadShapeService` to manage the shape list.
- Register the service in `MauiProgram.cs`.
- Refactor `CadCanvas.razor` to pass shapes to JavaScript.
- JS renders shapes dynamically based on passed data.

**Outcome:**  
Canvas is now driven by data from C# rather than hardcoded JS.

---

### 🖱️ Phase 4: UI Buttons & User Interaction

**Objective:** Let users add and clear shapes via UI.

- Add toolbar buttons: “Add Rectangle”, “Add Cylinder”, “Clear”.
- Connect buttons to C# event handlers that modify shape list.
- Refresh canvas rendering via JS interop after changes.
- Update UI reactively using `StateHasChanged()`.

**Outcome:**  
Users can interactively create or remove shapes.

---

### 💾 Phase 5: File Save/Load (.mycad Format)

**Objective:** Persist and retrieve project data.

- Define a `.mycad` file format (JSON with version and shape list).
- Add "Save" and "Load" buttons to toolbar.
- Serialize shapes to a JSON file.
- Deserialize `.mycad` files and reload shape list.
- Redraw canvas from loaded data.

**Outcome:**  
User projects can be saved and reopened at any time.

---

### 🔧 Phase 6 (Optional): Advanced Features

**Objective:** Add polish and interactive UX features.

- Add zoom and pan functionality (via JavaScript).
- Implement drag-and-drop for shape repositioning.
- Add snapping to grid and alignment guides.
- Support undo/redo functionality.
- Export to image (PNG) or vector (SVG).

**Outcome:**  
The app evolves into a refined, professional CAD tool.

---

## 📁 File Format

`.mycad` is a JSON-based custom file format. Example structure:

```json
{
  "version": 1,
  "shapes": [
    { "type": "rectangle", "x": 100, "y": 150, "width": 200, "height": 100 },
    { "type": "cylinder", "x": 300, "y": 200, "radius": 50, "height": 75 }
  ]
}
