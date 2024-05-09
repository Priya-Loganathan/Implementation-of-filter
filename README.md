# Implementation-of-filter

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step2
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step3
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.

### Step4
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step5
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.

### Step6
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.

## Program:
### Developed By : DELLI PRIYA L
### Register Number : 212222230029

### 1. Smoothing Filters

i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```

![328213196-33947cf9-4c63-475e-806c-390083a7c283](https://github.com/Priya-Loganathan/Implementation-of-filter/assets/121166075/4bacf49f-23b4-4e7d-8e7d-e0220510120b)


ii) Using Weighted Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```

![328213329-78e823d5-41d7-4bae-9e3d-6c20d4daf5d8](https://github.com/Priya-Loganathan/Implementation-of-filter/assets/121166075/ce248ffa-b9e2-41e2-87d7-61404ecf823b)


iii) Using Gaussian Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

![328213429-9356bb84-63b3-4348-95c1-3d8ffa906845](https://github.com/Priya-Loganathan/Implementation-of-filter/assets/121166075/9a33810b-3533-4966-a0d8-114a49d84ae3)

iv) Using Median Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```

![328213529-8aeef3fc-06ac-4e63-8893-bd8abf35e6bb](https://github.com/Priya-Loganathan/Implementation-of-filter/assets/121166075/afb7acc9-1007-4398-b9cd-fa6663f0a75b)

### 2. Sharpening Filters
i) Using Laplacian Kernal
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```

![328213685-befd4282-d370-4be6-b0f5-5afb3c374bf5](https://github.com/Priya-Loganathan/Implementation-of-filter/assets/121166075/b409bd14-a4ad-4760-81b4-ee5e5fe90710)

ii) Using Laplacian Operator
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dog.png')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

![328213790-991df694-38bc-4a2c-8248-8c68608f44b3](https://github.com/Priya-Loganathan/Implementation-of-filter/assets/121166075/0e6feb4f-c2c9-4c46-942a-d355d2da1f8f)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
