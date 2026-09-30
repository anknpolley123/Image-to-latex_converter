# 📷 Image to LaTeX Converter (Offline & Web-Native)

A lightweight, fully client-side web application built with pure **HTML5, CSS3, and JavaScript**. It allows users to capture handwritten or printed math equations directly using their mobile camera or file upload, run local Optical Character Recognition (OCR) inside the browser via WebAssembly, and instantly render formatted LaTeX equations using MathJax.

---

## ✨ Features

* **📷 Native Camera Integration:** Uses `capture="environment"` to trigger the rear camera directly on mobile devices (iOS & Android) without security blocks or HTTPS webcam restrictions.
* **🔒 100% Client-Side & Private:** Powered by **Tesseract.js** running in WebAssembly. Image processing happens entirely inside your browser—no backend servers or external API keys required.
* **📐 Live LaTeX Rendering:** Integrates **MathJax v3** to translate generated LaTeX syntax into visual mathematical formulas in real time.
* **📝 Smart Symbol Formatting:** Converts common ASCII math patterns (e.g., `sqrt(x)`, `>=`, `*`) into structured LaTeX syntax (e.g., `\sqrt{x}`, `\ge`, `\cdot`).
* **📱 Responsive Mobile UI:** Clean, card-based interface styled for desktop browsers and mobile screens alike.

---

## 🛠️ How It Works

[ Native Camera / Image File ]
│
▼
[ Hidden HTML5 Canvas Engine ] ──► (Generates Pixel Data)
│
▼
[ Tesseract.js (WASM Worker) ] ──► (Extracts Raw ASCII Text)
│
▼
[ RegEx LaTeX Parser ]         ──► (Formats to LaTeX Syntax)
│
▼
[ MathJax Engine ]             ──► (Renders Output Visuals)


1. **Capture:** The user takes a photo or selects an image via the native file input.
2. **Preprocessing:** The file is loaded onto an off-screen HTML `<canvas>` element.
3. **Local OCR:** Tesseract.js processes the canvas pixels locally using a WebAssembly background worker.
4. **Parsing:** A custom RegEx function translates common character sequences into valid LaTeX math notation.
5. **Rendering:** MathJax converts the LaTeX string into rendered math markup inside the DOM.

---

## 🚀 Getting Started

### Option 1: Direct File Usage (No Setup Required)
1. Download or clone this repository:
   ```bash
   git clone [https://github.com/your-username/image-to-latex.git]