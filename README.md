BlinkTrack

Hands-free cursor control through real-time gaze tracking and blink gestures.

BlinkTrack is a webcam-based interaction prototype that explores an alternative way to control desktop interfaces without a mouse. It estimates gaze direction to guide cursor movement and interprets intentional blink patterns as interaction commands.

The project combines computer vision, interaction design, and rapid prototyping to investigate how low-cost hardware can support hands-free computer access.

Highlights

Real-time gaze estimation from a standard webcam

Cursor movement driven by eye direction

Blink-based selection using Eye Aspect Ratio (EAR)

Support for single, double, and prolonged blink interactions

Independent demos for gaze tracking, blink detection, and cursor control

Integrated hands-free interaction prototype

Fitts' Law demo for evaluating pointing performance

Early interaction flows and interface mockups

Interaction Model

BlinkTrack separates continuous navigation from intentional selection:

Look toward a target to guide the cursor.

Hover to stabilize the target selection.

Blink intentionally to trigger an interaction.

Different blink patterns can be mapped to different commands, allowing the interface to distinguish deliberate actions from natural blinking.

Technology

Python for the application and experimental demos

MediaPipe Face Mesh for facial and eye landmark extraction

OpenCV for webcam capture and real-time frame processing

PyAutoGUI for desktop cursor control

Eye Aspect Ratio (EAR) for blink detection

Figma for interaction flows and low-fidelity prototypes

Project Structure

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

Prototype Screens

Cursor Tracking



Blink Interaction Flow



Gaze Hover



Getting Started

Requirements

Python 3.9 or newer

A working webcam

Permission to access the camera

Accessibility or input-control permission for cursor automation

Install the main dependencies:

pip install opencv-python mediapipe pyautogui numpy

Run the Application

From the repository root:

python src/main.py

Run the integrated tracking prototype directly:

python src/blinktrack_integrated.py

Run Individual Experiments

# Blink detection
python src/blink_detection/blink_test.py

# Gaze tracking
python src/gaze_tracking/gaze_test.py

# Cursor control
python src/cursor_control/cursor_test.py

# Pointing-performance demo
python src/fitts_demo.py

# Menu interaction demo
python src/menu_demo.py

Design Goals

Low-cost: operate using a conventional webcam rather than specialized eye-tracking hardware.

Hands-free: support cursor navigation and selection without a physical mouse.

Modular: keep gaze, blink, and cursor components independently testable.

Exploratory: make it easy to prototype and evaluate alternative gaze-and-blink interaction techniques.

Current Limitations

BlinkTrack is an experimental prototype rather than a production accessibility tool. Performance can vary with camera placement, lighting, head movement, glasses, facial geometry, and operating-system permissions. Extended use also requires careful calibration and protection against unintended cursor actions.

Safety

The cursor-control demos can move the system pointer automatically. Keep PyAutoGUI's fail-safe enabled and be prepared to terminate the process from the keyboard while testing.

Roadmap

User-specific gaze and blink calibration

Smoothing and adaptive cursor acceleration

Configurable blink-to-command mappings

Dwell-based selection as an alternative to blinking

False-positive suppression for natural blinks

Quantitative evaluation of speed, accuracy, and workload

Improved support for different lighting conditions and eyewear
