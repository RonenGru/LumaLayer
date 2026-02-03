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

# 📝 LumaLayer Project Tracker (v1.1 Dev Update)

### ✅ COMPLETED (Target: v1.1 - The Product Update)
*Focus: Turning Art into Physical Products & Hardware Precision.*

*   [x] **The Digital Cookie Cutter (Shaping Engine):**
    *   *Feature:* STL Exporter now respects transparency and "clips" the mesh.
    *   *Wall Builder:* Implemented a robust loop to generate vertical side-walls for cutouts.
    *   *interactive UI:* Added sliders for Scale, Horizontal Position, and Vertical Position.
    *   *Shape Library:* Built-in Circle, Oval, Square, Rounded Rect, Star, and Heart masks.
*   [x] **Keychain Loop Generator:**
    *   *Feature:* One-click checkbox to add a physical mounting loop to any shaped print.
*   [x] **LumaMeter Calibration Wizard:**
    *   *Issue:* Solved the "Cool White LED" color bias using software.
    *   *Workflow:* Built a 5-point Wizard (White, Black, Red, Green, Blue) to create a custom user profile.
    *   *Logic:* Implemented KNN (K-Nearest Neighbors) math to identify colors based on the user's specific sensor fingerprint.
*   [x] **"Train This Color" Logic:**
    *   *Feature:* Users can "teach" the meter exotic filaments (Bronze, Gold, Silk) and save them to the permanent profile.
*   [x] **Hybrid LumaMeter Sync:**
    *   *Fix:* Prevented LumaMeter from overwriting manual artistic color choices while still allowing Live TD physics updates.

---

### 🚨 IMMEDIATE POLISH (Next Session)
*Focus: Finalizing v1.1 for release.*

*   [ ] **Manual Profile Management:** Add a button to "Reset Calibration" or delete specific trained colors without editing JSON.
*   [ ] **Mask "Plastic" Preview:** Ensure the keychain loop is clearly visible in the UI by using a grey "plastic" filler for the mask areas.
*   [ ] **TD Slider Label Fix:** Ensure the TD value is visible in the library manager (Started).

---

### 🚀 FEATURE ROADMAP (v1.1 & Beyond)
*Focus: Ecosystem expansion.*

*   [ ] **Library Import:**
    *   *Task:* Write a parser for standard CSV filament lists (HueForge/Spreadsheets).
*   [ ] **AI Engine Upgrade:**
    *   *Task:* Transition from Torch (`.t7`) to ONNX (`.onnx`) for modern GPU support.
*   [ ] **Mac/Linux Port:**
    *   *Task:* Finalize Python cross-platform dependencies for a non-Windows release.
*   [ ] **Auto-Stack (From Guide):**
    *   *Task:* Automatically generate a 5-layer stack based on the "Guide" analysis.

***

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
