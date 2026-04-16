# Idea
The concept of a "glasses-free" digital experience is technically feasible by using gaze-contingent magnification to bypass the optical limitations of myopia or presbyopia. Since large objects remain legible even when blurred, a Desktop Application can use eye-tracking hardware (like Tobii) or webcam-based AI to detect exactly where a user is looking and project a dynamic zoom bubble at that location. By calibrating the zoom to a user's "Critical Print Size" and applying high-contrast filters, the software ensures that text is always large and sharp enough for the brain to process without corrective lenses. This approach is best implemented as a system-wide overlay using Python or Electron, allowing the "digital lens" to follow the user across any software, from web browsers to complex coding environments, effectively turning the monitor itself into a personalized assistive device.

# Prompt
"I want to build a Python-based accessibility tool for people with myopia that acts as a 'digital lens.' The goal is to allow users to read a monitor without glasses by using eye-tracking to provide dynamic zoom.
Core Requirements:
Tech Stack: Use Python with PyQt6 for the GUI and mss for high-speed screen capture.
The Overlay: Create a transparent, 'click-through' window that stays on top of all other applications.
Magnification Logic: Inside this window, render a 300x300 pixel 'zoom bubble.' This bubble must capture the screen area directly underneath it and scale it by a user-defined factor (e.g., 2x or 3x).
Gaze Integration: Use a placeholder function get_gaze_coordinates() that currently returns the mouse position, but structure it so I can easily swap in a Tobii Eye Tracker or WebGazer API later. The zoom bubble must follow these coordinates smoothly.
Visual Quality: Apply a sharpening filter or high-contrast adjustment to the magnified area to assist blurred vision.
Performance: Ensure the capture and render loop runs at 30+ FPS to prevent lag or motion sickness.
Please provide the full Python script for this prototype, including the logic for a transparent overlay that doesn't interfere with mouse clicks on windows behind it."

Pro-Tips for using the output:
Click-Through: Make sure the AI uses the Qt.WindowType.WindowTransparentForInput flag in PyQt; otherwise, you won't be able to click on buttons behind the zoom bubble.
Smoothing: Ask the AI to implement a Linear Interpolation (LERP) for the movement so the bubble doesn't "jitter" if the eye-tracking data is noisy.
Contrast: If the text is still hard to read, ask it to add a "Grayscale and Invert" toggle to the zoomed area.