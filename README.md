# Workshop--1-Adding-Sunglasses-to-Your-Passport-Photo-Using-OpenCV

### REG NO :212225230287

#### NAME :UDHAYA S

Sturdy-Octo-Disco-Adding-Sunglasses-for-a-Cool-New-Look
Sturdy Octo Disco is a fun project that adds sunglasses to photos using image processing.

Welcome to Sturdy Octo Disco, a fun and creative project designed to overlay sunglasses on individual passport photos! This repository demonstrates how to use image processing techniques to create a playful transformation, making ordinary photos look extraordinary. Whether you're a beginner exploring computer vision or just looking for a quirky project to try, this is for you!

# Features:
Detects the face in an image.
Places a stylish sunglass overlay perfectly on the face.
Works seamlessly with individual passport-size photos.
Customizable for different sunglasses styles or photo types.
Technologies Used:
Python
OpenCV for image processing
Numpy for array manipulations
How to Use:
Clone this repository.
Add your passport-sized photo to the images folder.
Run the script to see your "cool" transformation!
# Applications:
Learning basic image processing techniques.
Adding flair to your photos for fun.
Practicing computer vision workflows.
Feel free to fork, contribute, or customize this project for your creative needs!
# PROGRAM
~~~python
# Import libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Load the Face Image
faceImage = cv2.imread('pho.png')
plt.imshow(faceImage[:,:,::-1]);plt.title("Face")
faceImage.shape
# Load the Sunglass image with Alpha channel
# (http://pluspng.com/sunglass-png-1104.html)
glassPNG = cv2.imread('Sunglass.png',-1)
plt.imshow(glassPNG[:,:,::-1]);plt.title("glassPNG")# Resize the image to fit over the eye region
glassPNG = cv2.resize(glassPNG,(190,50))
print("image Dimension ={}".format(glassPNG.shape))
# Separate the Color and alpha channels
glassBGR = glassPNG[:,:,0:3]
glassMask1 = glassPNG[:,:,3]# Display the images for clarity
plt.figure(figsize=[15,15])
plt.subplot(121);plt.imshow(glassBGR[:,:,::-1]);plt.title('Sunglass Color channels');
plt.subplot(122);plt.imshow(glassMask1,cmap='gray');plt.title('Sunglass Alpha channel');# Resize the image to fit over the eye region
glassPNG = cv2.resize(glassPNG,(250, 80))
print("image Dimension ={}".format(glassPNG.shape))

# Separate color and alpha channels
glassBGR = glassPNG[:, :, :3]
glassMask1 = glassPNG[:, :, 3]

# Display sunglasses and alpha mask
plt.figure(figsize=(12,5))

plt.subplot(121)
plt.imshow(glassBGR[:,:,::-1])
plt.title("Sunglasses")

plt.subplot(122)
plt.imshow(glassMask1, cmap="gray")
plt.title("Alpha Mask")

plt.show()
# Make a copy
faceWithGlassesNaive = faceImage.copy()

# Place sunglasses over eyes
faceWithGlassesNaive[75:117, 126:256] = glassBGR

# Display
plt.figure(figsize=(8,10))
plt.imshow(faceWithGlassesNaive[:,:,::-1])
plt.title("Sunglasses Fitted")
plt.axis("on")
plt.show()
# Final Result
plt.figure(figsize=(12,8))

plt.subplot(121)
plt.imshow(faceImage[:,:,::-1])
plt.title("Original Image")
plt.axis("on")

plt.subplot(122)
plt.imshow(faceWithGlasses[:,:,::-1])
plt.title("With Sunglasses")
plt.axis("on")

plt.show()
~~~

#output:
<img width="487" height="492" alt="image" src="https://github.com/user-attachments/assets/25716250-86af-4277-af34-865a719f7d64" />

<img width="617" height="312" alt="image" src="https://github.com/user-attachments/assets/5a7d547d-5f9c-44cf-83b4-38769affcacb" />

<img width="775" height="123" alt="image" src="https://github.com/user-attachments/assets/c810d7d5-7c27-4458-b6ed-f4f46be8c123" />

<img width="770" height="115" alt="image" src="https://github.com/user-attachments/assets/6bf25f34-bbd3-4834-9f1b-51b219ceca59" />

<img width="777" height="376" alt="image" src="https://github.com/user-attachments/assets/fb09b105-d48f-4f34-8e72-4b133876b4e1" />



