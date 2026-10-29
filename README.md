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

## Contributing

Contributions are welcome! Since this is a single-file project, the workflow is simple:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/my-improvement`).
3. Make your changes in `index.html` (or split into modules if you prefer).
4. Test in at least two modern browsers (Chrome + Firefox recommended).
5. Open a pull request with a clear description of what changed and why.

Please keep the project dependency-free (no build tools, no frameworks) and maintain the privacy-first, client-side-only design.

---

## Support

- **Issues** — Open a GitHub issue for bugs or feature requests.
- **Discussions** — Use GitHub Discussions for general questions.
- **Contact** — Reach out via the contact link in the Creator section above.

This project is maintained in spare time. Response times may vary, but all reports are read.

---

> Built for the open web. 🌐

