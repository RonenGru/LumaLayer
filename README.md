# LumaLayer
LumaLayer is a professional, free tool for creating 3D filament paintings, backlit lithophanes, and flat pop-art from images.

# LumaLayer v1.1 (Coming Soon) 

## 🚀 The "Shaping Update"

LumaLayer v1.1 is a major evolutionary leap for the project. This update transforms the software from a 3D relief tool into a professional **Product Manufacturing Suite**, allowing users to go from a digital image to a retail-ready physical product (like keychains, badges, and coasters) in minutes.

---

## 🎨 The Digital Cookie Cutter (Shaping Engine)
*Exclusive to LumaLayer Pro*

The headline feature of v1.1 is the ability to physically "cut" your 3D prints into specific shapes. No more rectangular blocks—now your prints can take any form.

*   **Interactive Shape Library:** Use the new dropdown menu to instantly clip your image into **Circles, Ovals, Stars, Hearts, Squares,** or **Rounded Rectangles**.
*   **Precision Composing:** New sliders for **Mask Scale**, **Horizontal Position**, and **Vertical Position** allow you to frame your subject perfectly within the chosen shape.
*   **Keychain Loop Generator:** A one-click physical mounting loop can be added to the top of any shape. This loop is mathematically integrated into the 3D mesh for maximum strength.
*   **Procedural Raised Borders:** Add a solid physical rim around your shapes with adjustable **Border Width**. This gives your prints a clean, finished "merchandise" look.
*   **Custom Mask Import:** Load any transparent **.PNG** file to use as a custom 3D stencil. If you can draw it, LumaLayer can print it.

---

## 🔬 LumaMeter 2.0 Integration
We have moved the "intelligence" of the LumaMeter from the hardware firmware to the LumaLayer software, resulting in a massive increase in color accuracy.

*   **5-Point Calibration Wizard:** A guided setup process that teaches LumaLayer the specific spectral fingerprint of your device's LED. Calibrates for White, Black, Red, Green, and Blue.
*   **Smart Enrollment (Train This Color):** Users can now "Enroll" specific filament brands (e.g., "Esun Bronze"). The software takes a snapshot of the sensor data and links it to a custom visual color and TD value.
*   **Profile Manager:** A dedicated window to manage your trained filament signatures. Delete old entries or reset your base calibration with one click.
*   **Hybrid Sync:** The LumaMeter now updates physical **TD values** live while allowing you to "lock" manual artistic colors if the sensor's raw data doesn't match your creative vision.

---

## 👁️ High-Fidelity Simulation
The simulation window has been rebuilt to provide an honest "What You See Is What You Get" (WYSIWYG) experience.

*   **Realistic (Final) Mode:** A new rendering engine using **Exponential Beer-Lambert math**. It accurately simulates how light passes through specific TD values and reveals 0.08mm layer transitions.
*   **Slicer-Sync Precision:** The simulation math is now perfectly aligned with the STL exporter. No more "Missing Layers" or height discrepancies.
*   **Lighting & Contrast Sliders:** New **Brightness** and **Contrast** controls allow you to tune the on-screen preview to match your monitor's gamma or your intended physical display environment.
*   **Subsurface Scattering:** Realistic mode now includes a "Softness" pass that mimics the way light naturally diffuses through real plastic.

---

## 🛠️ Performance & Stability
*   **Slicer-Compatible Meshes:** Implemented vertex-snapping and "Despeckling" (Island removal) to eliminate "Floating Region" errors in Bambu Studio and OrcaSlicer.
*   **Float-Point Precision:** Improved rounding logic ensures the physical STL height matches the LumaLayer Recipe exactly to the micron.
*   **UI Polish:** Dynamic help labels now explain each simulation mode in real-time as you switch between them.

---

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
    [x] **Mask "Plastic" Preview:** Ensured the keychain loop is clearly visible in the UI by using a grey "plastic" filler for the mask areas.
*   [x] **LumaMeter Calibration Wizard:**
    *   *Issue:* Solved the "Cool White LED" color bias using software.
    *   *Workflow:* Built a 5-point Wizard (White, Black, Red, Green, Blue) to create a custom user profile.
    *   *Logic:* Implemented KNN (K-Nearest Neighbors) math to identify colors based on the user's specific sensor fingerprint.
*   [x] **"Train This Color" Logic:**
    *   *Feature:* Users can "teach" the meter exotic filaments (Bronze, Gold, Silk) and save them to the permanent profile.
*   [x] **Hybrid LumaMeter Sync:**
    *   *Fix:* Prevented LumaMeter from overwriting manual artistic color choices while still allowing Live TD physics updates.
*   [x] **TD Slider Label Fix:** Ensured the TD value is visible in the library manager.
*   [x] **Manual Profile Management:** Add a button to "Reset Calibration" or delete specific trained colors without editing JSON.

---

### 🚀 FEATURE ROADMAP (v1.2 & Beyond)
*Focus: Ecosystem expansion and professional product finishes.*

*   [ ] **Library Import:**
    *   *Task:* Write a parser for standard CSV filament lists (3D Filament Profile Database/Spreadsheets).
*   [ ] **AI Engine Upgrade:**
    *   *Task:* Transition from Torch (`.t7`) to ONNX (`.onnx`) for modern GPU support.
*   [ ] **Mac/Linux Port:**
    *   *Task:* Finalize Python cross-platform dependencies for a non-Windows release.
*   [ ] **Auto-Stack (From Guide):**
    *   *Task:* Automatically generate a 5-layer stack based on the "Guide" analysis.
*   [ ] **The "Scale to Content" Engine:**
    *   *Task:* Implement "Alpha-Cropping" logic so "Target Width" refers to the actual printed plastic, ignoring transparent empty space in the PNG file.
*   [ ] **The "Silent Edge" Vectorizer:**
    *   *Task:* Move from pixel-perfect masking to Vector-Simplified perimeters to eliminate jagged "staircase" edges and make the printer virtually silent.
*   [ ] **The LumaText Engine:**
    *   *Task:* Add a procedural text layer for keychains and badges (names, dates, or messages) using the "Raised Border" high-Z math.
*   [ ] **The "LumaPuzzle" Procedural Engine:**
    *   *Task:* Break images into random, interlocking puzzle pieces using Bezier-curve tabs with built-in "Slicer Gaps" (0.15mm - 0.25mm) for a perfect friction fit.

---

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
