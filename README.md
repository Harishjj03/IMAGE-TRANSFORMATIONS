# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>

### Step2:
<br>

### Step3:
<br>

### Step4:
<br>

### Step5:
<br>

## Program:
```
Developed By: JANARTHANAN K
Register Number: 212223040072

Transformations on Image
import cv2
import numpy as np
# Load the image
image = cv2.imread('your_image.jpg') # Replace with your image path
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
# ----------------------- Display Results with Matplotlib -----------------------

titles = [
    "Original", "Translated", "Scaled", "Sheared",
    "Horizontally Flipped", "Vertically Flipped",
    "Rotated", "Cropped"
]
images = [
    image, translated, scaled, sheared,
    h_flip, v_flip, rotated, cropped
]
plt.figure(figsize=(12, 10))
for i in range(len(images)):
    plt.subplot(3, 3, i + 1)  # 3 rows, 3 columns
    plt.imshow(images[i])
    plt.title(titles[i], fontsize=10)
    plt.axis("off")

plt.tight_layout()
plt.show()



```
## Output:

<img width="907" height="670" alt="image" src="https://github.com/user-attachments/assets/dcb69e26-71a2-4bee-94a8-8ee035389ade" />



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
