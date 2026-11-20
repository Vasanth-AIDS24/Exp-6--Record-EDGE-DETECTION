# EX. No: 6 – EDGE DETECTION
### Developed By : Vasanth P
### Register Number : 212224230295
### Aim :
To implement various edge detection techniques using Python and OpenCV to identify and highlight the edges and boundaries of objects in an image.
### Requirements :
Hardware Requirements:
- Computer or Laptop
- Minimum 4 GB RAM
Software Requirements:
- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib
### Procedure :
1. Import the required libraries such as OpenCV, NumPy, and Matplotlib.
2. Read the input image using cv2.imread().
3. Convert the original image into grayscale using cv2.cvtColor().
4. Display the original image using Matplotlib.
5. Apply the Sobel Edge Detection method in X and Y directions.
6. Combine both Sobel directions using cv2.magnitude().
7. Apply the Laplacian Edge Detection method to identify rapid intensity changes.
8. Apply the Canny Edge Detection method using threshold values 50 and 150.
9. Display the detected edges using Matplotlib.

### Program : 
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('ex.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('on')
```
```python
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('on')
```
```python
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('on')
```
```python
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('on')
```

### Output : 


<img width="348" height="491" alt="image" src="https://github.com/user-attachments/assets/e1a48d19-1686-46e2-823f-a4ee2754b141" />


<img width="345" height="492" alt="image" src="https://github.com/user-attachments/assets/bf448c8f-c1a2-4ef7-9884-b5b976655a1a" />


<img width="347" height="493" alt="image" src="https://github.com/user-attachments/assets/adeb7b2c-1fd2-4a1f-8450-46e063ef773f" />


<img width="342" height="500" alt="image" src="https://github.com/user-attachments/assets/4224ee33-1b61-4e8a-af3c-e801129dc680" />












### Result :
Thus, various edge detection techniques such as Sobel, Laplacian, and Canny were successfully implemented using Python and OpenCV. The edges and boundaries of objects in the input image were identified and displayed successfully.
