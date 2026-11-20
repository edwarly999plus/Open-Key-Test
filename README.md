# OpenKeyTest

**OpenKeyTest** (`v1.0.0`) is a free, open-source web tool designed to run real-time interactive diagnostics on keyboards, mechanical *switches*, function keys, and media controls directly in the browser—no extra software installation required.

---

## Key Features

- **4-state visual detection:**
  - **Gray (Untested):** Key has not been pressed yet.
  - **Green (Detected OK):** Key detected properly (bright green while held down, soft green when released).
  - **Blue (System / Media Function):** Identifies special keys for brightness, volume, media playback, lock, screenshot, and the `Fn` key.
  - **Red (Faulty):** Lets you manually mark broken or unresponsive keys by **right-clicking** them or enabling **Faulty Mark Mode**.
- **Multi-Layout & Language Support:**
  - `QWERTY` — English (USA)
  - `QWERTY` — Español (LATAM)
  - `AZERTY` — Français (France)
  - `QWERTZ` — Deutsch (Deutschland)
  - `Dvorak` — Simplified
- **Operating System Compatibility:** Dynamically switches modifier key labels and mappings between **Windows** (`Win`, `Ctrl`, `Alt`) and **macOS** (`Command ⌘`, `Control ⌃`, `Option ⌥`).
- **Keyboard Form Factors:**
  - **Laptop (75%):** Compact layout with an integrated function row and arrow keys.
  - **With Numpad (100%):** Full standard keyboard with a navigation cluster and *NumPad*.
  - **Full Extended:** Adds dedicated brightness and volume controls above the numeric keypad.
- **System / Media Function Tester:** Dedicated bar for testing physical or virtual keys for brightness (`Br-`/`Br+`), volume, media (`Prev Track`, `Play / Pause`, `Next Track`), lock, hibernate, project/display, mic mute, airplane mode, magnifier, and home / new tab.
- **Synthesized Sound Feedback (Web Audio API):** Generates real-time sound effects with no external audio files, featuring volume control and selectable profiles:
  - *Mechanical Clicky (Blue)*
  - *Mechanical Tactile (Brown)*
  - *Soft Membrane*
  - *Muted*
- **Event Inspector & Telemetry:** Displays live `event.key`, `event.code`, and `keyCode` values, a progress percentage bar, key counters (tested, functions, faulty, and total), and a history of the last 24 keystrokes.
- **PNG Export:** Generates and downloads a clean high-resolution snapshot (`OpenKeyTest_Teclado_YYYY-MM-DD.png`) showing only the status legend and keyboard map via `html2canvas`.

---

## Technologies Used

- **HTML5 & JavaScript (Vanilla ES6+):** Self-contained single-file architecture with zero build dependencies (*zero-build*).
- **Tailwind CSS (CDN):** Modern dark-mode UI with a *glassmorphism* design.
- **Web Audio API:** Procedural keystroke sound synthesis (*noise bursts* and oscillators) in the browser.
- **html2canvas:** Direct export of the visual diagnostic view to a PNG image.
- **Google Fonts:** *Inter* and *JetBrains Mono* typefaces.

---

## Installation and Usage

Because this is a self-contained static web application in a single file (`OpenKeyTest.html`), it requires no complex servers or package managers:

### 1. Clone the repository

```bash
git clone [https://github.com/edwarly999plus/Open-Key-Test.git](https://github.com/edwarly999plus/Open-Key-Test.git)
cd Open-Key-Test

```

### 2. Run the application

* **Option A (Direct):** Double-click `OpenKeyTest.html` to open it directly in any modern browser (Chrome, Firefox, Edge, Safari, Brave).
* **Option B (Local server):** If you prefer serving it over local HTTP:

```bash
# Using Python 3
python -m http.server 8080

```

Then open `http://localhost:8080/OpenKeyTest.html` in your browser.

---

## Quick Diagnostic Guide

| Action | Result |
| --- | --- |
| **Press any physical key** | Lights up the key in **green** (or **blue** if it is a media/system key) and logs its telemetry. |
| **Right-click a key** | Marks or unmarks the key in **red** as faulty. |
| **`Faulty Mark Mode` button** | Lets you mark faulty keys using a **left click** (ideal for touchscreens or *trackpads*). |
| **`Function Keys` button** | Shows or hides the top `F1–F12` row and the media bar. |
| **`Reset Test` button** | Resets all tested keys back to gray while keeping faulty key marks. |
| **`Save PNG` button** | Downloads an image of the current keyboard state for technical reports or warranty claims. |

---

## Contributing

Contributions are welcome. If you want to add new keyboard layouts (such as Spanish ISO, Portuguese ABNT2, or Japanese JIS), improve event detection, or report a bug:

1. **Fork** the project.
2. Create a branch for your improvement (`git checkout -b feature/new-layout`).
3. Make your changes and *commit* them (`git commit -m "Add ISO-ES layout"`).
4. Push your changes to your branch (`git push origin feature/new-layout`).
5. Open a **Pull Request**.

---

## License

This project is distributed under the MIT license — see the `LICENSE` file in the repository for more details.

```

```
