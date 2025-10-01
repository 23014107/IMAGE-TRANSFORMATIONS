# IMAGE-TRANSFORMATIONS


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
Developed By:
Register Number:

import cv2
import numpy as np
# Load the image
image = cv2.imread('/content/ramya photo.jpg') # Replace with your image path
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
### i)Image Translation
<br><img width="432" height="535" alt="image" src="https://github.com/user-attachments/assets/c5dadf01-d846-45d1-bc25-898765146341" />

### ii) Image Scaling
<br><img width="436" height="546" alt="image" src="https://github.com/user-attachments/assets/634dbc7f-e6b0-483d-b34a-819801349e88" />



### iii)Image shearing
<br><img width="637" height="407" alt="Screenshot 2025-10-01 181104" src="https://github.com/user-attachments/assets/99ba5949-1f57-4a8a-bf8b-6e98ff27ddeb" />



### iv)Image Reflection
<br><img width="625" height="477" alt="image" src="https://github.com/user-attachments/assets/f593def7-7560-4fd8-8eb9-f5cfddd3880d" />




### v)Image Rotation
<br>
<br>
<br>
<br>



### vi)Image Cropping
<br>
<br>
<br>
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
