# QRForge — Image ↔ QR Code Converter

A free, privacy-first web app that converts images into QR codes and back again. Built with vanilla JavaScript, HTML, Tailwind CSS, and the Canvas API. Everything runs locally in your browser — no uploads, no servers, no tracking.

![Status](https://img.shields.io/badge/status-stable-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Backend](https://img.shields.io/badge/backend-none-success)
![Dependencies](https://img.shields.io/badge/runtime-CDN%20only-lightgrey)

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [How It Works](#how-it-works)
- [Capacity Rules](#capacity-rules)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Browser Support](#browser-support)
- [Limitations](#limitations)
- [Troubleshooting](#troubleshooting)
- [Future Recommendations](#future-recommendations)
- [Contributing](#contributing)
- [Support](#support)
- [License](#license)
- [Acknowledgements](#acknowledgements)
- [Creator / Designer](#creator--designer)

---

## Overview

QRForge is a single-page web application with **two core features**:

1. **Image → QR Code** — Upload, drag, or paste any image, and QRForge compresses it into a scannable QR code.
2. **QR Code → Image** — Upload, drag, or paste a QR code to recover the original image.

All processing happens **entirely in the browser** using the Canvas API. Images are never uploaded, stored, or transmitted anywhere.

> **Important:** Because QR codes have a hard capacity limit (~2.9 KB at error correction level L), the recovered image is a compressed thumbnail — not a full-resolution copy.

---

## Features

- 🔁 **Bi-directional conversion** — image to QR and QR back to image
- 📥 **Three input methods** — drag & drop, file browse, or clipboard paste (`Ctrl/⌘ + V`)
- 🔒 **100% private** — no backend, no uploads, no analytics on user files
- 🎛️ **Tunable output** — adjust detail level and error correction strength
- 🧠 **Adaptive compression** — automatically scales and re-encodes the image to fit the QR payload budget
- 🌗 **Dark mode** — toggle with persistence via `localStorage`
- 📱 **Fully responsive** — mobile-first layout with a collapsible nav
- 💾 **Download support** — save generated QR codes and recovered images as files
- 📊 **Live metadata** — shows payload size, QR version, module count, dimensions, and file size
- ⚡ **Instant results** — no queues, no spinners that hang; generation and decoding complete in well under a second
- 🖼️ **Print-ready output** — QR codes render at high resolution with a proper quiet zone

---

## Tech Stack

| Layer | Technology |
| --- | --- |
| Markup | HTML5 |
| Styling | [Tailwind CSS](https://tailwindcss.com/) (CDN build) |
| Logic | Vanilla JavaScript (ES2017+) |
| QR generation | [`qrcode`](https://www.npmjs.com/package/qrcode) v1.5.3 |
| QR decoding | [`jsQR`](https://github.com/cozmo/jsQR) v1.4.0 |
| Fonts | [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts |

No build step. No bundler. Just open the HTML file.

---

## Getting Started

### Option 1 — Run locally

# Clone the repository
git clone https://github.com/your-username/qrforge.git
cd qrforge

# Open in your browser
open index.html       # macOS
# or
xdg-open index.html   # Linux
# or
start index.html      # Windows

---

## Changelog

### v1.0.0 — Initial release
- Image → QR encoding with adaptive compression
- QR → image decoding with multi-scale scanning
- Drag & drop, file browse, and clipboard paste input
- Dark mode with persistence
- Fully responsive single-file build
- Download support for both directions

Future versions will follow [Semantic Versioning](https://semver.org/).

---

## FAQ

**How much image data actually fits in a QR code?**
About 2.9 KB at error correction level L. That's enough for a small JPEG thumbnail — roughly 200–400 px on the long edge, depending on complexity.

**Does the quality slider affect scan reliability?**
Yes. Higher detail produces denser QR codes (more modules), which are harder for older cameras or printed copies to read. If a code won't scan, drop to **Compact** and retry.

**Can I scan the QR with my phone directly from the screen?**
Yes. Display the generated QR at a comfortable size on a bright screen and point your phone camera at it. Screen scanning usually works better than small printed copies.

**Does this work offline?**
Almost — the QR libraries (`qrcode` and `jsQR`) are loaded from a CDN. Once the page has loaded, no further network requests are made. For full offline support, see the PWA recommendation in [Future Recommendations](#future-recommendations).

**Is there a file size limit?**
Yes — 10 MB per input image, enforced client-side to avoid memory issues. The encoder will still compress it down to a few KB for the QR.

---

## Version

**Current release:** `v1.0.0`

---

<p align="center">
  <sub>QRForge is released under the MIT License. QR Code is a registered trademark of DENSO WAVE INCORPORATED.</sub>
</p>
