# Laser Pointer Detection with OpenCV

This project is a Python application designed to detect a laser pointer through a webcam feed using OpenCV. It can identify the position of the laser pointer within a 2-meter range with a tolerance of 10 cm, making it suitable for applications requiring precise laser tracking.

## Table of Contents
- [Project Overview](#project-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Customization](#customization)
- [Known Issues](#known-issues)
- [License](#license)

---

## Project Overview

This application captures video frames from a webcam, processes them using OpenCV, and identifies a laser pointer by detecting specific color ranges. The code is designed to work with a red laser pointer but can be adjusted to detect other colors by modifying the color range values.

The program uses:
- **Color Filtering** to isolate the laser pointer's color.
- **Contour Detection** to find the laser pointer's exact location in the frame.
- **Center Marking** to highlight the detected laser pointer in real-time.

## Installation

Ensure you have Python installed on your machine. Then, install the required libraries.

### Step 1: Install OpenCV

To install OpenCV, run the following command in your terminal or command prompt:

```bash
pip install opencv-python
```

### Step 2: Install NumPy

NumPy is required for numerical operations in OpenCV. You can install it using:

```bash
pip install numpy
```

## Usage

1. **Connect a Webcam**: Ensure your webcam is connected and functioning properly.
2. **Run the Code**: Use the following command to start the laser pointer detection:

    ```bash
    python laser_pointer_detection.py
    ```

3. **Quit the Program**: Press 'q' on your keyboard to stop the detection and close the program.

## Customization

### Adjusting Color Range

By default, the code is configured to detect a red laser pointer. To adjust it for other colors, modify the `lower_red` and `upper_red` variables in the code.

```python
# Example for a red laser pointer
lower_red = np.array([160, 100, 100])
upper_red = np.array([180, 255, 255])
```

You may need to experiment with these values to achieve accurate results based on your laser pointer's color.

### Changing Detection Range

The detection range (up to 2 meters) and tolerance (10 cm) are based on the camera's resolution and setup. Adjustments may be necessary for different camera configurations or environments.

## Known Issues

- **Lighting Conditions**: Performance may vary in different lighting conditions. It is recommended to test the application in both bright and dim lighting to ensure accurate detection.
- **Camera Calibration**: If distance detection seems inaccurate, consider calibrating your camera for better accuracy. Adjustments to the `GaussianBlur` and `contourArea` filters may also help.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
