# IMAGE-TRANSFORMATIONS
## Name: HARISHBALA J
## Register no:212224223002

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.


### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.
2.Scaling resizes the image by scaling factors.
3.Shearing distorts the image along one axis.
4.Reflection flips the image horizontally or vertically.
5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.


## Program:
DEVELOPED BY : HARISHBALA J
REGISTER NUMBER :212224223002
```



import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 1: Load the image
image = cv2.imread('VI.jpeg')  # Load the image from file
# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off') 
(np.float64(-0.5), np.float64(1279.5), np.float64(812.5), np.float64(-0.5))

i)Image Translation

tx, ty = 100, 50  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  # Display the translated image
plt.title("Translated Image")  
plt.axis('off')
(np.float64(-0.5), np.float64(1279.5), np.float64(812.5), np.float64(-0.5))

ii) Image Scaling

fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
# resize: Resize the image by scaling factors fx, fy
# INTER_LINEAR: Uses bilinear interpolation for resizing
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')
(np.float64(-0.5), np.float64(6399.5), np.float64(1625.5), np.float64(-0.5))

iii)Image shearing

shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')
(np.float64(-0.5), np.float64(1279.5), np.float64(812.5), np.float64(-0.5))

iv)Image Reflection

reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)
# flip: 1 means horizontal flip, 0 would be vertical flip, -1 would flip both axes
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')
(np.float64(-0.5), np.float64(1279.5), np.float64(812.5), np.float64(-0.5))


v)Image Rotation

(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')
(np.float64(-0.5), np.float64(1279.5), np.float64(812.5), np.float64(-0.5))


vi)Image Cropping

x, y, w, h = 100, 100, 200, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
# The crop is performed by slicing the image array in the y and x directions
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')
(np.float64(-0.5), np.float64(199.5), np.float64(149.5), np.float64(-0.5))


```
## Output:

### Original Image


<img width="515" height="508" alt="Screenshot 2026-02-03 102635" src="https://github.com/user-attachments/assets/68f7dbe0-2375-4d25-bed5-1d9a24008193" />




### i)Image Translation



<img width="513" height="514" alt="Screenshot 2026-02-03 102642" src="https://github.com/user-attachments/assets/ea1bf0c4-94b0-4a71-b8a3-7de306076134" />

### ii) Image Scaling

<img width="706" height="354" alt="Screenshot 2026-02-03 102647" src="https://github.com/user-attachments/assets/1748bdb4-8614-498f-bdc1-74d2db4b9b5c" />



### iii)Image shearing


<img width="525" height="508" alt="Screenshot 2026-02-03 102653" src="https://github.com/user-attachments/assets/76c9b261-3a45-498e-9ba1-17c49b237e89" />



### iv)Image Reflection

<img width="445" height="515" alt="Screenshot 2026-02-03 102701" src="https://github.com/user-attachments/assets/e4f55caf-d3ac-4989-8600-b8287fab7273" />


### v)Image Rotation

<img width="391" height="496" alt="Screenshot 2026-02-03 102708" src="https://github.com/user-attachments/assets/cbff6a49-6f6b-44b1-a60d-f44763d5bc43" />


### vi)Image Cropping
<img width="607" height="494" alt="Screenshot 2026-02-03 102716" src="https://github.com/user-attachments/assets/03149d0e-3dcd-4579-827d-63da62dae991" />




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
