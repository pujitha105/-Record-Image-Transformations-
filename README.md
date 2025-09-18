# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm :
### Step 1 :

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step 2 :


Read the input image using cv2.imread() and store it in a variable for further processing.

### Step 3 :

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis. 2.Scaling resizes the image by scaling factors. 3.Shearing distorts the image along one axis. 4.Reflection flips the image horizontally or vertically. 5.Rotation rotates the image by a given angle.

### Step 4 :


Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step 5 :


Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program :
```
Developed By: k.pujitha
Register Number: 212223240074

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Chennai_Central.jpg')
image.shape
# Display the images.
plt.imshow(image[:,:,::-1])
plt.title('Original Image')
plt.show()

# i) Image Translation
tx, ty = 100, 200  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (636, 438))
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis('on')
plt.show()
# Image Scaling
fx, fy = 2.0, 1.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(scaled_image[:,:,::-1]) 
plt.title("Scaled Image") 
plt.axis('on')
plt.show()
# Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (636, 438))
plt.imshow(sheared_image[:,:,::-1])
plt.title("Sheared Image") 
plt.axis('on')
plt.show()

# Image Reflection
reflected_image = cv2.flip(image, 2)
# Show original image 
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('off')

# Show reflected image 
plt.subplot(1, 2, 2)
plt.imshow(reflected_image[:,:,::-1])
plt.title("Reflected Image")
plt.axis('off')

plt.tight_layout()
plt.show()
# Image Rotation
(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')
image .shape

angle = 145  
center = (636 // 2, 438 // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
plt.imshow(rotated_image[:,:,::-1])  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')
plt.show()

# Image Cropping
x, y, w, h = 0, 0, 200, 150  
cropped_image = image[y:y+h, x:x+w]
# Show original image 
plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis('on')

# Show reflected image 
plt.subplot(1, 2, 2)
plt.imshow(cropped_image[:,:,::-1])
plt.title("Cropped Image")
plt.axis('on')

plt.tight_layout()
plt.show()
```
## Output:
<img width="573" height="416" alt="image" src="https://github.com/user-attachments/assets/79b3d6fc-1291-4ddc-a457-59de42f7ad07" />
<img width="596" height="414" alt="image" src="https://github.com/user-attachments/assets/33ec83ba-5d08-45fc-b13d-93d14c9ea089" />
<img width="628" height="241" alt="image" src="https://github.com/user-attachments/assets/3021f691-9e76-4db8-a7a4-688853405184" />

<img width="585" height="408" alt="image" src="https://github.com/user-attachments/assets/c3af8744-93d0-4e33-95fb-7dc13dc7eae6" />
<img width="754" height="288" alt="image" src="https://github.com/user-attachments/assets/44e4e770-57dc-4967-a07b-78e130058658" />
<img width="598" height="412" alt="image" src="https://github.com/user-attachments/assets/918fe055-0803-4dd1-a28c-9cc534212629" />
<img width="552" height="386" alt="image" src="https://github.com/user-attachments/assets/8c5a43fe-11b3-4188-a14e-b67ddb46ec35" />
<img width="773" height="335" alt="image" src="https://github.com/user-attachments/assets/cef80f7d-bcfb-48b7-aa96-1000bac85486" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
