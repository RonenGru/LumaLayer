# LumaLayer
LumaLayer is a professional, free tool for creating 3D filament paintings, backlit lithophanes, and flat pop-art from images.

# 📝 LumaLayer Project Tracker

### 🚨 IMMEDIATE FIXES (Target: v1.0.2 Patch)
*Focus: Critical usability bugs and UI scaling.*

*   [x] **High-DPI / 4K Scaling:**
    *   *Issue:* UI is tiny on 4K screens; Mouse clicks drift on laptops (125% scale).
    *   *Fix:* Implemented `SetProcessDpiAwareness(2)` + Manual "View -> Zoom" Menu (100% - 200%).
*   [x] **Layer Sorting Logic:**
    *   *Report:* Zantium reported that moving layers Up/Down in the UI does not update the Simulation order.
    *   *Task:* Check `move_layer` function to ensure it triggers a full stack rebuild.
*   [x] **TD Value Save Bug:**
    *   *Report:* TD values sometimes get mixed up or don't save correctly when adding multiple custom filaments.
    *   *Task:* Audit the `save_to_lib` and `load_from_lib` functions.
*   [x] **Magic Lift UX:**
    *   *Issue:* Turning off the "Lift" toggle disables the effect. Users want to hide the Green Mask but keep the 3D Lift active.
    *   *Task:* Separate "Show Mask" (Visual) from "Enable Lift" (Physics).
	
	### 🛠️ NEXT UPDATE (Target: v1.0.3 & Firmware v2.3)
*Focus: Color Accuracy & UX Polish*

*   [ ] **LumaMeter Firmware (v2.3):**
    *   *Issue:* OLED reports "Green" for Yellow/Bronze filaments due to Cool White LED bias.
    *   *Solution:* Implement **Automatic White Balance (AWB)** on startup (scan white target) and switch internal math to **HSV (Hue-Saturation-Value)** for reliable color detection.
*   [ ] **Software Color Matching:**
    *   *Issue:* App guesses generic names ("Grey") instead of using the user's saved library names ("Bronze").
    *   *Solution:* Update logic to search `filament_library.json` for a close match *before* falling back to generic web colors.
*   [ ] **UI Logic Fix (Zones Mode):**
    *   *Issue:* TD Slider is disabled in "Zones" view.
    *   *Solution:* Enable TD slider in all views to allow data entry without switching tabs.

---

### 🚀 FEATURE ROADMAP (Target: v1.1)
*Focus: New capabilities and workflow improvements.*

*   [ ] **Library Import:**
    *   *Request:* Thierry asked to import HueForge/CSV filament libraries.
    *   *Task:* Write a parser for standard CSV filament lists.
*   [ ] **AI Engine Upgrade:**
    *   *Task:* Upgrade from Torch (`.t7`) to ONNX (`.onnx`) support. Allows for modern custom style training on NVIDIA GPUs.
*   [ ] **Mac/Linux Port:**
    *   *Task:* Investigate compiling with PyInstaller on non-Windows machines.
	
	*Focus: Workflow Automation & Compatibility*

*   [ ] **Library Import / Migration:**
    *   *Request:* Import CSV/JSON libraries from other tools (3DFilamentProfiles).
    *   *Task:* Write a parser to convert external formats into `filament_library.json`.
*   [ ] **Auto-Stack (From Guide):**
    *   *Request:* Button to automatically generate a 4-5 layer filament stack based on the "Guide" K-Means analysis.
*   [ ] **AI Engine Upgrade:**
    *   *Task:* Upgrade from Torch (`.t7`) to ONNX (`.onnx`) support for modern style training.

---



## 🛠️ v1.0.2 Patch Notes (Jan 22, 2026)

This update addresses critical feedback from the launch and improves the experience for 4K and High-DPI users.

### 🔍 UI & Scaling
*   **4K Support:** Added a manual **View -> Zoom** menu. Users on high-resolution monitors can now scale the UI from 100% up to 200% for readability.
*   **Mouse Accuracy:** Implemented high-precision coordinate mapping. Clicks and X-Ray hovers are now pixel-perfect across all Windows scaling levels (100%, 125%, 150%, etc.).

### 🥞 Filament Stack & Workflow
*   **Smart Sorting:** Added a **Sort ↕** button to the stack. Instantly reorder your UI list to match the physical printing order (Base to Top).
*   **Magic Lift UX:** Separated mask visibility from the physics engine. You can now hide the "Green Mask" to see your art clearly while keeping the 3D lift effect active.
*   **New Project Button:** Added a one-click **"New Project / Clear"** button to reset the stack and settings instantly.

### 💾 Library & Stability
*   **Auto-Custom Detection:** The software now automatically detects when a preset is modified and switches the label to "Custom" to prevent accidental overwrites.
*   **Smart Save Dialog:** The Save Filament window now pre-fills with the existing name for faster editing.
*   **Installer Polish:** Added a custom Uninstaller Icon and refined the installation folder to remove redundant files.
