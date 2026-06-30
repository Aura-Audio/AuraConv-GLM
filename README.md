# AuraConv — Real-Time Convolution Filter & Audio Playground

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/Web_Audio_API-4A154B?logo=webaudio&logoColor=white" alt="Web Audio API">
  <img src="https://img.shields.io/badge/AudioWorklet-8A2BE2" alt="AudioWorklet">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License MIT">
</p>

**AuraConv** is a professional-grade, real-time audio manipulation tool that runs entirely in the browser.  
It combines a **variable-length block processor**, **colored noise generators**, **3D HRTF spatial rotation**, and a **convolution reverb** – all driven by an `AudioWorklet` for glitch-free, low-latency performance.  

Whether you want to turn a microphone into a rhythmic gate, create evolving noise drones, or explore phase-cancellation effects, AuraConv gives you immediate, tactile control over every parameter.

---

## Overview

AuraConv is a single-page web application built on the modern Web Audio API.  
Its heart is a custom `AudioWorklet` processor that chops incoming audio (mic, noise, or both) into **variable-length blocks**, applies a **dry/wet convolution reverb**, and passes the result through an **HRTF panner** for 3D spatialization.

All parameters – block size (1 – 100,000 samples), duration, polarity inversion, LFOs, and noise colour – can be adjusted **in real time** without audio drop-outs.  
A built-in **preset system** lets you save, export, import, and share your favourite configurations.

---

## Features

### Audio Sources
- **Microphone** – Process live audio with echo cancellation disabled for raw capture.
- **Colored Noise** – Eight noise types: White, Pink, Brown, Blue, Purple, Green, Grey, Black.
- **Mic + Noise** – Layer microphone input with noise for hybrid textures.

### Block Processing (Variable-Length Gate)
- **Block Samples** – Set any block length from **1 sample** (Nyquist-rate chopping) up to **100,000 samples** (approx 2.3 s at 44.1 kHz).
- **Block Duration** – Percentage of each block that is affected (1% – 99%).
- **Polarity Inversion** – Invert phase on microphone, noise, or both for cancellation effects.
- **Invert Blocking Polarity** – Swap between silencing the block portion and passing **only** the block portion (chopped bursts).

### Modulation Engines
- **Auto-Loop Samples** – Triangular sweep of block size between configurable min/max values.
- **Auto-Loop Noise Colors** – Cycle through all eight noise colours at adjustable speed.
- **Volume LFO** – Triangle-wave modulation of master volume (0% -> 100% -> 0%) with visual meter.
- **Spatial Rotation** – 3D HRTF panning that rotates the sound source around the listener's head (rate from 0.05 Hz to 3 Hz). Headphones recommended.

### Spatial & Ambient Effects
- **Convolution Reverb** – Generated decaying-noise impulse response with adjustable decay (0.5 – 12 s) and dry/wet mix.
- **HRTF Panner** – Full-sphere positioning; integrates with rotation for immersive spatial movement.

### Preset Management
- **8 factory presets** covering granular textures, drones, phase-swept pads, and percussive cutters.
- **Save, Delete, Export** (JSON) and **Import** user presets.
- Default presets cannot be deleted – a safe starting point for experimentation.

### User Interface & Visualisation
- **Dark / Light theme** with persistent preference.
- Real-time **frequency spectrum**, **waveform**, and **RMS volume meter**.
- Colour-coded visualisation adapts to active modulation sources and noise colour.
- Collapsible control sections for a clean, uncluttered workspace.
- Keyboard shortcut (`Space`) to start/stop audio.

### Technical Highlights
- **AudioWorklet** for rock-solid, low-latency processing in a dedicated audio thread.
- **Single-file HTML** – no build step, no dependencies; just open the file.
- **Logarithmic sliders** for the huge block-size range, giving precise control at low values.
- **Background/visibility handling** – warns when the tab is hidden and audio may pause.

---

## Getting Started

1. **Clone or download** the repository:

```bash
   git clone https://github.com/your-username/auraconv.git
```

2. Open index.html in a modern browser (Chrome, Firefox, Edge, Safari).
   Note: Microphone access requires a secure context (HTTPS or localhost).
   For local development, use a simple server like python -m http.server or the Live Server extension in VS Code.
3. Click "Start Audio" and grant microphone permission if prompted.
4. Explore the presets or tweak the controls to create your own sound.

---

Technology Stack

Layer Technology
Audio Processing Web Audio API, AudioWorklet
Graphics HTML5 Canvas
UI Vanilla HTML / CSS / JS, CSS Variables
Storage localStorage for presets & theme
Build None – a single, self-contained HTML file

---

Roadmap

Planned features and improvements – contributions are welcome!

· Custom Impulse Responses – Load user-provided IR files for convolution reverb.
· More Noise Types – Violet, velvet, and custom spectral-shaped noise.
· MIDI Control – Map any parameter to MIDI CC for hardware integration.
· Multi-Channel Output – Separate outputs for dry/wet or spatial channels.
· Audio Export / Recording – Capture output to WAV or MP3.
· Advanced Visualisation – 3D spectrum, oscilloscope modes, and vector scopes.
· Mobile-First Layout – Better touch responsiveness and compact UI mode.
· Parameter Automation Envelopes – Draw custom modulation curves.
· Community Preset Library – Share and browse presets directly from the app.
· WebAssembly-accelerated DSP – For even more complex real-time effects.

---

Contributing

Contributions, issues, and feature requests are highly appreciated!

1. Fork the repository.
2. Create a feature branch (git checkout -b feature/amazing-feature).
3. Commit your changes (git commit -m 'Add amazing feature').
4. Push to the branch (git push origin feature/amazing-feature).
5. Open a Pull Request.

Please ensure your code follows the existing style and is thoroughly tested.

---

License

Distributed under the MIT License. See LICENSE for more information.

---

Acknowledgements

· Built with the standard Web Audio API and AudioWorklet – no external libraries.
· Inspired by modular synthesis, granular effects, and experimental sound design tools.

---

<p align="center">
  <sub>Made with ❤️ for sound explorers and tinkerers.</sub>
</p>
```
