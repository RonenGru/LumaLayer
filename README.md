# LumaLayer: The Filament Painting & Merchandise Factory

LumaLayer is a professional physics-based engine for creating 3D filament paintings, backlit lithophanes, and retail-ready physical products from any image.

---

## 🚀 NEW: LumaLayer v1.5 — The "Multi-Material & Dither" Release
The **v1.5 "Multi-Material"** update transforms LumaLayer into a professional multi-color dither workspace. Create dithered, multi-material photo paintings with zero CAD experience.

### 🏁 LumaMix Studio (Dithering & Color Pop)
*Exclusive to LumaLayer Pro*
*   **Dither Engines:** Generate high-frequency photographic dithered assemblies using Floyd-Steinberg or organic Riemersma space-filling Hilbert curve algorithms.
*   **Independent Pop Color Boosts:** Brighten and saturate specific color regions independently. Boosting a layer's dither density allows you to "punch up" background colors in the slicer [1].
*   **Shadow Nuance (Gamma Curve):** Adjust the non-linear Gamma curve, Contrast, and Brightness in real-time. Gamma allows you to control how quickly dither dots fade into the dark base plate, keeping details visible without washing out highlights.

### 🧩 The Jigsaw Factory & Packaging
*Exclusive to LumaLayer Pro*
*   **Procedural Puzzles:** Instantly convert any image into a real, interlocking jigsaw puzzle.
*   **Adjustable "Snap-Fit":** Built-in tolerance sliders (0.05mm - 0.40mm) ensure your puzzle pieces fit together perfectly regardless of your printer's calibration.
*   **Assembly Mats & LumaBox:** Generate custom-fitted Assembly Mats (Inlay or Border modes) and automatic, sliding-lid LumaBox packaging. Uses 3-sided symmetrical rail math for a smooth, professional slide-feel.

### 🗺️ LumaMural Tiling (Large-Format Prints)
*Exclusive to LumaLayer Pro*
*   **Modular Grid Slicing:** Print massive, wall-sized creations by slicing your designs into a modular tile grid.
*   **Beveled Joint Math:** Automatically applies 2D beveled joint slopes to the edges of each tile. This ensures that dither patterns and solid features fade down cleanly at the joints, guaranteeing tight, seamless physical assembly.

### 🔡 Personalization, Shaping & Borders
*Exclusive to LumaLayer Pro*
*   **Multi-Line Text Overlay:** Add 3D-stamped names, dates, or logos. Supports vertical stacking and auto-centering.
*   **The Digital Cookie Cutter:** Crop your art into **Circles, Ovals, Stars, Hearts, Squares,** or **Rounded Rectangles**. One-click keychain loop generator and raised outer borders are fully supported.
*   **Dilation Outline Buffering:** Automatically applies a 1-pixel dilation safety buffer (via OpenCV) around your text and outer borders. This prevents dither dots from printing inside letter notches (e.g., the letter "V") or touching your text walls, keeping sliced text razor-sharp [1].

### 🧱 Flat Art Studio
*Exclusive to LumaLayer Pro*
*   **Vector Assembly Exporter:** Turn logos, signs, and vectors into multi-part STL/3MF assemblies without the complexity of traditional CAD software.
*   **Edge-Preserving Cartoonizer:** Features a built-in preprocessor combining Bilateral Filtering and Posterization. Easily convert complex, textured photographs into clean, solid, flat-color segments for vector-style 3D printing [2].

---

## 🔬 LumaMeter v3.0 Hardware Integration
The LumaLayer ecosystem includes the **LumaMeter**, an open-source hardware device for measuring the exact Transmissive Distance (TD) of your filaments.

*   📶 **WiFi Connection:** Link your LumaMeter wirelessly via Thierry’s Precision Firmware.
*   ⚡ **Instant Mapping:** Scan your filament and watch the TD and Hex values update in your software live.
*   🪄 **Calibration Wizard:** Software-side 5-point calibration to ensure perfect color accuracy.
*   [**Build your own LumaMeter (Guide)**](https://github.com/RonenGru/LumaLayer/wiki/LumaMeter%E2%80%90Build%E2%80%90Guide) | [**Flash Firmware (Web Installer)**](https://ronengru.github.io/LumaLayer/flash.html)

---

## 📝 Project Tracker & Patch Notes

### ✅ v1.5 MULTI-MATERIAL DITHER (Current Release)
*   [x] **LumaMix Studio:** Floyd-Steinberg and Riemersma dither engines with real-time preview and export.
*   [x] **Independent Color Boosts:** Dynamic, mask-specific dither density boosting [1].
*   [x] **LumaMural Tiling:** Multi-part large-format slicing with automatic beveled joint generation.
*   [x] **Edge-Preserving Cartoonizer:** Bilateral + Posterization preprocessor inside Flat Art Studio [2].
*   [x] **Standard-Compliant 3MF Assembly:** Standard `<components>` packaging that groups sub-meshes relative to a shared `(0,0,0)` origin, completely resolving "floating region" and "empty initial layer" errors [1].
*   [x] **Outline Buffering:** Prevent dither dots from bleeding into text and border perimeters [1].
*   [x] **Full-State Saving:** Zipped `.lula` project format now losslessly compresses and saves mask layer arrays as binary PNGs alongside all LumaMix and Flat Art variables [1].

### ✅ v1.2 GOLD MASTER
*   [x] **LumaPuzzle:** Procedural Jigsaw generator with adjustable tolerances.
*   [x] **LumaBox:** Sliding-lid packaging generator.
*   [x] **Multi-Line Text:** Textbox integration with vertical stacking logic.
*   [x] **Slicer-Sync Physics:** Implemented +0.001mm geometry logic for 0.08mm layer height reliability.

### ✅ v1.1 THE SHAPING UPDATE
*   [x] **The Cookie Cutter:** Preset shapes and Keychain Loop generator.
*   [x] **LumaMeter 2.0:** KNN spectrography logic and Calibration Wizard.

---

## 🚀 Future Roadmap (v2.0 & Beyond)
LumaLayer is constantly evolving. Here is what we are currently researching and developing for future updates:

- **🍎 Mac/Linux Support:** Finalizing cross-platform dependencies for a non-Windows release.
- **⚡ ONNX AI Integration:** Transitioning to modern GPU-accelerated AI styles for near-instant processing.
- **📐 Vector Perimeter Smoothing:** Procedural path simplification to eliminate "staircase" edges on high-resolution prints.

---

## 🛠️ Stability & Performance
LumaLayer is built for reliability. Our recent "Multi-Material" hardening included:

- **Parent-State Persistence:** Settings for LumaMix and Flat Art Studio are managed directly on the parent window, keeping your sliders in sync even if the sub-windows are closed during session saves.
- **DPI-Aware Layouts:** Unified horizontal layouts that dynamically center and size dither previews to prevent aspect-ratio stretching and border-cropping on narrow screens [1].
- **Slicer-Sync Precision:** Standard-compliant XML assembly packaging that allows multi-part 3MF files to load cleanly on unmodified, official releases of Bambu Studio and OrcaSlicer [1].

---

## 📥 Get Started
- **Download Pro/Free:** [LumaLayer Ko-Fi Shop](https://ko-fi.com/createwithtech)
- **User Manual:** [Official Wiki](https://github.com/RonenGru/LumaLayer/wiki)
- **Video Tutorials:** [CreateWithTech on YouTube](https://www.youtube.com/@CreatewithTech)
- **Community:** [Join our Discord](https://discord.gg/RNgHYxhQff)

*Created by Ronen (CreateWithTech) | © 2026 All Rights Reserved*
