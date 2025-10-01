# IMAGE-TRANSFORMATIONS
# Name : RAMYA.P
# Register Number: 212223240137

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
<br>Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
<br>Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:
<br>Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
<br>Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```python
Developed By: RAMYA.P
Register Number: 212223240137

import cv2
import numpy as np
# Load the image
image = cv2.imread('/content/Screenshot 2025-10-01 181914.png') # Replace with your image path
(h, w) = image.shape[:2]
# ----------------------- Translation -----------------------
# Move image 100 pixels right and 50 pixels down
tx, ty = 100, 50
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])
translated = cv2.warpAffine(image, translation_matrix, (w, h))
# ----------------------- Scaling -----------------------
# Resize by 1.5x horizontally and 0.75x vertically
scaled = cv2.resize(image, None, fx=1.5, fy=0.75, interpolation=cv2.INTER_LINEAR)
# ----------------------- Shearing -----------------------
# Shear image horizontally
shear_matrix = np.float32([[1, 0.5, 0], [0, 1, 0]]) # x-shear
sheared = cv2.warpAffine(image, shear_matrix, (int(w + 0.5*h), h))
# ----------------------- Reflection (Flipping) -----------------------
# Flip horizontally (mirror image)
h_flip = cv2.flip(image, 1)
# Flip vertically
24
v_flip = cv2.flip(image, 0)
# ----------------------- Rotation -----------------------
# Rotate by 45 degrees around the center
angle = 45
scale = 1.0
center = (w // 2, h // 2)
rotation_matrix = cv2.getRotationMatrix2D(center, angle, scale)
rotated = cv2.warpAffine(image, rotation_matrix, (w, h))
# ----------------------- Cropping -----------------------
# Crop a region (top-left 200x200)
cropped = image[0:200, 0:200]
# ----------------------- Display Results -----------------------

# Plot the original and transformed images
from google.colab.patches import cv2_imshow

cv2_imshow(image)
cv2_imshow(translated)
cv2_imshow(scaled)
cv2_imshow(sheared)
cv2_imshow(h_flip)
cv2_imshow(v_flip)
cv2_imshow(rotated)
cv2_imshow(cropped)

```
## Output:
<img width="930" height="532" alt="image" src="https://github.com/user-attachments/assets/902f1605-bf7d-40d8-8980-d4c67c7e5a20" />
<img width="930" height="532" alt="image" src="https://github.com/user-attachments/assets/f8d7e927-1d12-4051-9f17-e7d229defe2f" />

<img width="1395" height="399" alt="image" src="https://github.com/user-attachments/assets/9a87ec73-cfaf-44ef-baf4-d85ac4aa51be" />
<img width="1196" height="532" alt="image" src="https://github.com/user-attachments/assets/02609c66-c87a-41ff-b31f-d11198e2b0f6" />

<img width="930" height="532" alt="image" src="https://github.com/user-attachments/assets/d77f798c-a8b9-4bd7-a3be-989311634368" />

<img width="930" height="532" alt="image" src="https://github.com/user-attachments/assets/0d7ebb3e-df5d-428c-ab51-d302112a6325" />


<img width="930" height="532" alt="image" src="https://github.com/user-attachments/assets/793bc580-6a7d-475d-a855-b1c119b86215" />




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
