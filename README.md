# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required libraries and images for the experiment

### Step2:
Translate the image using wrapAffine and the same can be used for Shearing the image

### Step3:
Use cv2.resize() to scale the image

### Step4:
use cv2.flip(img,2) to get the reflected image

### Step5:
Crop the image by using slicing

## Program:

### Developed By:SABARINATH R
### Register Number:212223100048
i)Image Translation
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('exp 5 img.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB) 
plt.imshow(image_rgb)
plt.title("Original Image")

rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
ii) Image Scaling
```
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
iii)Image shearing
```
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
iv)Image Reflection
```
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')

```
v)Image Rotation
```
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
vi)Image Cropping
```
cropped_image = image_rgb[20:600, 75:700]  
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show() 
```
## Output:
### original Image:
![Screenshot 2025-04-12 145625](https://github.com/user-attachments/assets/cc412c8e-1bf8-4526-b839-aeffa9cff681)

### i)Image Translation
![Screenshot 2025-04-12 145633](https://github.com/user-attachments/assets/4e27dc7f-482b-4af5-9fe8-8d4bb82a40d0)

### ii) Image Scaling
![Screenshot 2025-04-12 145641](https://github.com/user-attachments/assets/fd22ed37-054e-419e-acf3-4812e49d3ecd)

### iii)Image shearing
![Screenshot 2025-04-12 145701](https://github.com/user-attachments/assets/ad755a7e-5568-48c2-8ee4-d2581b1bc6ed)

### iv)Image Reflection
![Screenshot 2025-04-12 145711](https://github.com/user-attachments/assets/d8424c19-7997-4252-88e5-99fb58fefc73)

### v)Image Rotation
![Screenshot 2025-04-12 145718](https://github.com/user-attachments/assets/19efee60-febf-48cf-9188-7700204bbede)

### vi)Image Cropping
![Screenshot 2025-04-12 145724](https://github.com/user-attachments/assets/6421c7cd-9a30-4991-a03e-f7bab3df41a7)

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
