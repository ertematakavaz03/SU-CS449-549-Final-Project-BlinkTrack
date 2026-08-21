# BlinkTrack

**Hands-free cursor control through real-time gaze tracking and blink gestures.**

BlinkTrack is a webcam-based interaction prototype that explores an alternative way to control desktop interfaces without a mouse. It estimates gaze direction to guide cursor movement and interprets intentional blink patterns as interaction commands.

The project combines computer vision, interaction design, and rapid prototyping to investigate how low-cost hardware can support hands-free computer access.

## Highlights

* Real-time gaze estimation from a standard webcam
* Cursor movement driven by eye direction
* Blink-based selection using Eye Aspect Ratio (EAR)
* Support for single, double, and prolonged blink interactions
* Independent demos for gaze tracking, blink detection, and cursor control
* Integrated hands-free interaction prototype
* Fitts' Law demo for evaluating pointing performance
* Early interaction flows and interface mockups

## Interaction Model

BlinkTrack separates continuous navigation from intentional selection:

1. **Look** toward a target to guide the cursor.
2. **Hover** to stabilize the target selection.
3. **Blink** intentionally to trigger an interaction.

Different blink patterns can be mapped to different commands, allowing the interface to distinguish deliberate actions from natural blinking.

## Technology

* **Python** — application logic and experimental demos
* **MediaPipe Face Mesh** — facial and eye landmark extraction
* **OpenCV** — webcam capture and real-time frame processing
* **PyAutoGUI** — desktop cursor control
* **Eye Aspect Ratio (EAR)** — blink detection
* **Figma** — interaction flows and low-fidelity prototypes

## Project Structure

```text
prototypes/
└── figma/
    ├── Cursor tracking mockup.png
    ├── blink flow (interaction flow).png
    └── gaze hover.png

src/
├── blink_detection/
│   └── blink_test.py
├── cursor_control/
│   └── cursor_test.py
├── gaze_tracking/
│   └── gaze_test.py
├── blinktrack_integrated.py
├── fitts_demo.py
├── main.py
└── menu_demo.py
```

## Prototype Screens

### Cursor Tracking

![Cursor tracking mockup](prototypes/figma/cursor-tracking-mockup.png)

### Blink Interaction Flow

![Blink interaction flow](prototypes/figma/blink-interaction-flow.png)

### Gaze Hover

![Gaze hover prototype](prototypes/figma/gaze-hover.png)

## Getting Started

### Requirements

* Python 3.9 or newer
* A working webcam
* Permission to access the camera
* Accessibility or input-control permission for cursor automation

Install the main dependencies:

```bash
pip install opencv-python mediapipe pyautogui numpy
```

### Run the Application

From the repository root:

```bash
python src/main.py
```

Run the integrated tracking prototype directly:

```bash
python src/blinktrack_integrated.py
```

### Run Individual Experiments

#### Blink Detection

```bash
python src/blink_detection/blink_test.py
```

#### Gaze Tracking

```bash
python src/gaze_tracking/gaze_test.py
```

#### Cursor Control

```bash
python src/cursor_control/cursor_test.py
```

#### Pointing-Performance Demo

```bash
python src/fitts_demo.py
```

#### Menu Interaction Demo

```bash
python src/menu_demo.py
```

## Design Goals

* **Low-cost:** Operate using a conventional webcam rather than specialized eye-tracking hardware.
* **Hands-free:** Support cursor navigation and selection without a physical mouse.
* **Modular:** Keep gaze, blink, and cursor components independently testable.
* **Exploratory:** Make it easy to prototype and evaluate alternative gaze-and-blink interaction techniques.

## Current Limitations

BlinkTrack is an experimental prototype rather than a production accessibility tool. Performance can vary with camera placement, lighting, head movement, glasses, facial geometry, and operating-system permissions.

Extended use requires careful calibration and protection against unintended cursor actions.

## Safety

The cursor-control demos can move the system pointer automatically. Keep PyAutoGUI's fail-safe enabled and be prepared to terminate the process from the keyboard while testing.

## Roadmap

* User-specific gaze and blink calibration
* Smoothing and adaptive cursor acceleration
* Configurable blink-to-command mappings
* Dwell-based selection as an alternative to blinking
* False-positive suppression for natural blinks
* Quantitative evaluation of speed, accuracy, and workload
* Improved support for different lighting conditions and eyewear
