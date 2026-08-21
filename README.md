# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `tony.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Ex. No: 03
### Histogram of an Images

### Developed By:
**Name: Sameer SHariff M** 

### Register No:
212224220085

# Import Python necessary libraries

img = cv2.imread('hyena.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

# Histogram Equalization for Color Images

img = cv2.imread('hyena.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  



<img width="715" height="439" alt="Screenshot 2026-08-21 093528" src="https://github.com/user-attachments/assets/8431d023-c9c4-463a-b31a-cf26ec8b3fce" />


<img width="816" height="547" alt="Screenshot 2026-08-21 093538" src="https://github.com/user-attachments/assets/4830418e-515c-47ac-842e-22dd74f7f44e" />

  
<img width="739" height="541" alt="Screenshot 2026-08-21 093547" src="https://github.com/user-attachments/assets/20523718-53ed-47b0-9e70-fe2a6bafc2f8" />

<img width="749" height="451" alt="Screenshot 2026-08-21 093557" src="https://github.com/user-attachments/assets/243c1009-63e8-4f78-a740-81e4284d525a" />

<img width="773" height="442" alt="Screenshot 2026-08-21 093601" src="https://github.com/user-attachments/assets/63135e17-70c6-4163-8093-74fdfc1d155a" />

<img width="798" height="552" alt="Screenshot 2026-08-21 093605" src="https://github.com/user-attachments/assets/9e2ae1df-8b8a-4a7d-ad0e-a91b78d90d92" />

<img width="1384" height="385" alt="Screenshot 2026-08-21 093617" src="https://github.com/user-attachments/assets/00238ff6-54f3-4f5e-a2d2-9e2ec11db6cb" />

<img width="1380" height="410" alt="Screenshot 2026-08-21 093627" src="https://github.com/user-attachments/assets/c6b990d4-4415-4ca2-b0eb-1645524127b4" />



---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
