# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.
```
img = cv2.imread('img1.jpg')

import cv2
import matplotlib.pyplot as plt

filename = list(uploaded.keys())[0]

img = cv2.imread(filename)

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img)
plt.title('Original Image')
plt.axis('off')
plt.show()
```

### Step 4:
Apply Averaging Filter using `cv2.blur()`.
```
avg = cv2.blur(img, (5, 5))

plt.imshow(avg)
plt.title('Averaging Filter')
plt.axis('off')
plt.show()
```

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.
```
kernel = np.array([[1, 2, 1],
                   [2, 4, 2],
                   [1, 2, 1]], dtype=np.float32)

kernel = kernel / np.sum(kernel)

weighted = cv2.filter2D(img, -1, kernel)

plt.imshow(weighted)
plt.title('Weighted Averaging Filter')
plt.axis('off')
plt.show()
```

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.
```
gaussian = cv2.GaussianBlur(img, (5, 5), 0)

plt.imshow(gaussian)
plt.title('Gaussian Filter')
plt.axis('off')
plt.show()
```

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.
```
median = cv2.medianBlur(img, 5)

plt.imshow(median)
plt.title('Median Filter')
plt.axis('off')
plt.show()
```

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.
```
lap_kernel = np.array([[0, -1, 0],
                       [-1, 5, -1],
                       [0, -1, 0]])

lap_kernel = lap_kernel.astype(np.float32)

lap_sharp = cv2.filter2D(img, -1, lap_kernel)

plt.imshow(lap_sharp)
plt.title('Laplacian Sharpening using Kernel')
plt.axis('off')
plt.show()
```

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.
```
gray = cv2.cvtColor(img, cv2.COLOR_RGB2GRAY)

laplacian = cv2.Laplacian(gray, cv2.CV_64F)

laplacian = cv2.convertScaleAbs(laplacian)

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Operator')
plt.axis('off')
plt.show()
```

### Step 10:
Display all filtered images using a grid layout for comparison.
```
images = [img, avg, weighted, gaussian, median,
          lap_sharp, laplacian]

titles = ['Original Image',
          'Averaging Filter',
          'Weighted Averaging',
          'Gaussian Filter',
          'Median Filter',
          'Laplacian Kernel',
          'Laplacian Operator']

plt.figure(figsize=(15, 12))

for i in range(7):
    plt.subplot(3, 3, i + 1)

    if i == 6:
        plt.imshow(images[i], cmap='gray')
    else:
        plt.imshow(images[i])

    plt.title(titles[i])
    plt.axis('off')

plt.tight_layout()
plt.show()
```

---

##  Developed By

- **Name:** SUBITHA S
- **Register No:** 212225040432 

---

##  Output

### Smoothing Filters

- Averaging filter produces blurred image

  <img width="507" height="411" alt="image" src="https://github.com/user-attachments/assets/48a63da5-ad8d-4eeb-9824-8d1cc64abec7" />

- Weighted averaging provides smoother result with less distortion

  <img width="507" height="411" alt="image" src="https://github.com/user-attachments/assets/55546efb-d84b-4c0e-9b64-7bcb41c929ec" />

- Gaussian filter preserves edges better while reducing noise

  <img width="507" height="411" alt="image" src="https://github.com/user-attachments/assets/0ac7d43f-8c8c-4d58-b200-c36e7a2f697a" />

- Median filter removes salt-and-pepper noise effectively

   <img width="507" height="411" alt="image" src="https://github.com/user-attachments/assets/3cc0ecb4-ade4-4676-961d-cdf94afe9f31" />


###  Sharpening Filters

- Laplacian kernel enhances edges and fine details

  <img width="507" height="411" alt="image" src="https://github.com/user-attachments/assets/729ff35a-4ced-4297-b0c8-5a29ad8c79ca" />

- Laplacian operator detects edges clearly in grayscale

  <img width="507" height="411" alt="image" src="https://github.com/user-attachments/assets/4877319b-7127-4d0c-93c8-09871f415183" />

  <img width="1489" height="1191" alt="image" src="https://github.com/user-attachments/assets/7b78e001-ced1-4c84-8cb9-fe2521a6c4bd" />



---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
