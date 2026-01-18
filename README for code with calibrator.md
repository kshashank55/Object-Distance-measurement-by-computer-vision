Markdown
# 📏 Universal Object & Distance Detector

A Python-based computer vision tool that detects objects using **Edge Detection** and calculates their distance from the camera in real-time. Unlike color-based trackers, this works on any object with a visible outline.

## 🚀 Features
* **Universal Detection:** Detects any object based on edges (Canny Edge Detection).
* **Real-time Distance:** Calculates distance in inches using the Pinhole Camera Model.
* **Live Tuning:** Includes on-screen sliders to adjust sensitivity and object size instantly.

## 🛠️ Prerequisites

You need **Python 3** and the **OpenCV** library installed.

```bash
pip install opencv-python numpy
🏃‍♂️ How to Run
Connect a webcam to your computer.

Open your terminal or command prompt in the folder containing the script.

Run the following command:

Bash
python detector.py
Note: Do not run this in Jupyter Notebook or Google Colab. It requires a native window for the live video feed.

⚙️ How to Use
Hold up an object (e.g., a phone, book, or box).

Adjust the "Threshold" Slider:

Move the slider until the green box tightly wraps around your object.

If the box is flickering or selecting the background, increase the threshold.

Adjust the "Object Width" Slider:

Input the real-world width of the object you are holding (in inches).

Example: If holding a standard playing card, set slider to 2.5.

Example: If holding a standard smartphone, set slider to 3.0 or 4.0.

Read the Distance:

The green text above the box displays the estimated distance in inches.

🧠 How it Works
Grayscale: Converts the frame to black and white.

Blur: Reduces noise to prevent false edge detection.

Canny Edge Detection: Finds high-contrast edges in the image based on your "Threshold" setting.

Contours: Connects edges to form shapes. The code selects the largest shape.

Math: Uses the formula: $$ Distance = \frac{\text{Real Width} \times \text{Focal Length}}{\text{Pixel Width}} $$

📐 Calibration (Optional)
For the most accurate results, calibrate the FOCAL_LENGTH variable in the code:

Place an object with a known width (e.g., 5 inches) exactly 24 inches away.

Note the pixel width (w) detected by the code.

Calculate: New Focal Length = (w * 24) / 5.

Update line 8 in detector.py with this new number.
