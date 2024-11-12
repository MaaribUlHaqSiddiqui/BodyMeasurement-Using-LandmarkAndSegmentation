## Body Measurement Script:

This Python script uses MediaPipe and PixelLib to calculate various body measurements such as waist, shoulders, arms, and legs from an image of a person. The script utilizes two main techniques: landmarking (via MediaPipe) and instance segmentation (via PixelLib's pointrend_resnet50.pkl model) to detect body landmarks and segment the body region from the image.

### Requirements:
Before running the script, you need to install the following packages:

- mediapipe: For body landmark detection
  - Run: pip install mediapipe opencv-python pixellib numpy
- opencv-python: For image processing
- pixellib: For instance segmentation using the pointrend_resnet50.pkl model
  - Additionally, you need to download the pointrend_resnet50.pkl model from PixelLib's GitHub repository or from the official PixelLib website, and place it in the same directory as your script.

### Running the Script
The script will prompt you to enter your height in inches. This is used to convert measurements from pixels to real-world units (inches).

#### Example
- Input Image: A full-body image of a person standing straight with arms open.
- Output: The script will detect the body landmarks, segment the body region, and calculate distances like waist, arms, shoulders, etc. The final image will show these measurements along with arrows pointing to each body part.
#### How it Works
1. Landmark Detection
The script uses MediaPipe's Holistic model to detect key body landmarks such as shoulders, elbows, knees, and more. The landmarks are then used to calculate the distance between various body parts.

2. Body Segmentation
PixelLib’s pointrend_resnet50.pkl model is used to perform instance segmentation. This step extracts the segmented body from the image, helping to focus on the body region for measurement calculation.

3. Distance Calculation
Using the Euclidean distance formula, the script calculates the physical distances between key body landmarks (e.g., from shoulder to shoulder, waist to waist). These distances are then converted from pixels to real-world measurements (inches) using the user's height.

### Notes
The best results will be obtained when the person in the image has their arms open and is standing straight.
If the arms or body are not fully visible or if the person is in a non-upright position, the measurements may be compromised
