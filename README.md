# Ninja Fruit 2011

**Deterministic blade-to-produce interaction engine. Single file. Zero dependencies. No data egress.**

Ninja Fruit 2011 is a browser-based blade simulation platform delivering real-time produce dispersion events. The application reconstructs the tactile experience of high-velocity bladed produce contact in a fully client-side execution environment. No server, no telemetry, no build step, no package manager, no node_modules, no corporate sponsorship.

**Live instance:** [nutrition-glad-ball-path.trycloudflare.com](https://nutrition-glad-ball-path.trycloudflare.com)

---

## Overview

The platform simulates the vertical displacement of six produce classes (watermelon, apple, orange, banana, pineapple, kiwi) and one ordnance class (fusible device, colloquially "bomb") within a two-dimensional gravity field. Operator input is captured through pointer events and evaluated against a segment-proximity model to determine blade contact. Successful contact triggers a deterministic dispersion sequence: fruit subdivision, juice particle emission, and scoring state transition.

The application is a faithful recreation of the 2011 mobile produce-slicing genre, preserved as a single self-contained HTML document for maximum archival fidelity.

---

## Badges

| Status | Value |
|--------|-------|
| Build | [![Build](https://img.shields.io/badge/build-single_file-brightgreen)](https://github.com/sloptop-the-terrible/ninja-fruit-2026) |
| Dependencies | [![Deps](https://img.shields.io/badge/dependencies-zero-brightgreen)](https://github.com/sloptop-the-terrible/ninja-fruit-2026) |
| Telemetry | [![Telemetry](https://img.shields.io/badge/telemetry-none-blue)](https://github.com/sloptop-the-terrible/ninja-fruit-2026) |
| Gravity model | [![Gravity](https://img.shields.io/badge/gravity-900_px_s2-orange)](https://github.com/sloptop-the-terrible/ninja-fruit-2026) |

---

## Features

### Produce Simulation

- Six produce classes with per-class mass, radius, and dispersion characteristics
- Watermelon, apple, orange, banana, pineapple, kiwi
- Randomized spawn trajectory with difficulty-scaled velocity profiles
- Rotational dynamics during flight
- Gravity field applied at 900 px/s² with velocity damping

### Blade Contact Model

- Pointer capture with sub-segment slicing detection
- Minimum swipe velocity threshold to prevent accidental activation
- Segment-to-circle proximity evaluation against all active entities
- Visual slash trail rendering with temporal decay
- Synthesized whoosh audio on high-velocity swipe

### Dispersion Physics

- Deterministic fruit subdivision into two hemispherical fragments
- Juice particle emission (14 particles per dispersion event)
- Fragment rotation, momentum inheritance, and independent trajectories
- Lifetime-based alpha decay for particle and fragment rendering

### Ordnance Handling

- Fusible device with active spark emission, failsafe on contact
- Screen-space disruption on ordnance activation
- Life state decrement with three-life capacity model
- Game termination on life state exhaustion

### Progression Systems

- Combo multiplier for multi-entity dispersion within a single swipe
- Difficulty ramp based on session duration
- Local high-score persistence via browser storage
- No account system, no leaderboards, no cloud sync

### Audio Architecture

- Web Audio API synthesis, zero audio assets shipped
- Distinct waveforms for swipe, dispersion, ordnance, combo, and termination events
- Audio context initialization on first user gesture (browser policy compliance)

---

## Architecture

The entire application is a single HTML document containing:

| Layer | Technology | Responsibility |
|-------|-----------|----------------|
| Rendering | Canvas 2D | Frame composition, entity drawing, particle systems |
| Input | Pointer Events API | Unified touch/mouse blade capture |
| Audio | Web Audio API | Procedural sound synthesis |
| State | In-memory | Game state machine, entity lists, scoring |
| Persistence | localStorage | High-score retention (opt-out available) |

### Execution Flow

1. Document loads, canvas initializes at device pixel ratio
2. Title screen presented, audio context deferred until first gesture
3. Operator gesture begins session, gravity model activates
4. Spawn scheduler emits produce and ordnance entities on difficulty curve
5. Pointer motion evaluated against entity positions each frame
6. Dispersion events mutate score, combo, and particle state
7. Termination on life exhaustion, high score persisted

---

## Installation

### Prerequisites

- Any modern browser with Canvas 2D and Pointer Events support
- No build tools, no runtime, no network connection required after download

### Procedure

```sh
# Clone the repository
git clone https://github.com/sloptop-the-terrible/ninja-fruit-2026.git

# Serve the directory (any static file server)
python3 -m http.server 8080

# Navigate to http://localhost:8080
```

Alternatively, open `index.html` directly in a browser. The application functions identically from the local filesystem.

---

## Privacy

Ninja Fruit 2011 makes **zero network requests** under any execution path.

| Data Class | Collected | Transferred | Stored |
|------------|-----------|-------------|--------|
| Produce position data | Temporary | No | No |
| Slice trajectory data | Temporary | No | No |
| High score | Local only | No | Browser localStorage |
| Telemetry | Never | No | No |
| Advertising identifiers | Never | No | No |
| User identity | Never | No | No |

No cookies. No fingerprinting. No third-party scripts. No content delivery network. The application is fully functional with the network interface disconnected.

---

## Threat Model

| Threat | Mitigation |
|--------|-----------|
| Unauthorized data exfiltration | Zero network code paths exist |
| Supply chain compromise | Single file, no dependencies, no build step |
| Malicious package injection | No package manager involvement |
| Third-party script injection | No third-party scripts |
| Telemetry collection | No analytics hooks, no beaconing |
| Browser storage poisoning | High score validated as integer, clamped |

---

## Standards Compliance

| Standard | Status |
|----------|--------|
| ECMAScript 5 strict mode | Compliant |
| Pointer Events API | Compliant |
| Canvas 2D API | Compliant |
| Web Audio API | Compliant |
| RFC 2324 (Hyper Text Coffee Pot Control Protocol) | Not applicable, no coffee pots |
| RFC 3092 (Etymology of "Foo") | Not applicable, no foo entities |

---

## Roadmap

### Q3 2026

- Additional produce classes
- Blade trail color theming
- Accessibility pass for pointer-reduced operators

### Q4 2026

- Deterministic replay recording
- Offline score attestation
- Gravitational field configuration interface

### H1 2027

- Multi-canvas federation
- Produce provenance ledger
- Quantum-resistant high-score signing

---

## FAQ

**Q: Does this application require an internet connection?**
A: No. After the initial download, the application runs entirely from local execution.

**Q: How is the high score stored?**
A: In browser localStorage. Clearing site data resets the score. No server involvement.

**Q: Is there a mobile version?**
A: The application is responsive and supports touch input through the Pointer Events API.

**Q: Are the sound effects royalty-free?**
A: The sound effects are synthesized in real time by the Web Audio API. No audio files exist to license.

**Q: What happens when the ordnance device is contacted?**
A: A life is lost and the screen experiences a disruption effect. Three contacts terminate the session.

---

## Contribution

Contributions are evaluated against the following criteria:

1. Single-file architecture preserved
2. Zero new dependencies
3. Zero network requests added
4. Deterministic dispersion physics maintained
5. 2011 genre fidelity respected

Pull requests that violate any criterion will be rejected. Issues that request feature creep will be closed with reference to this policy.

---

## License

**ICE-WARE LICENSE**

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, subject to the following conditions:

1. The Software shall not be served at a temperature above 0 degrees Celsius.
2. The Software shall not be used to chill beverages of any kind.
3. The Software shall not be transported across international borders without a signed manifest.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
