# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** manorajapriyan.l.e 
- **Register Number:** 212225040227

  ### Ex. No. 01

#### 1. Read the image ('1.jpg') using OpenCV imread() as a grayscale image.
```python
img = cv2.imread('1.jpg', cv2.IMREAD_COLOR)
```

#### 2. Print the image width, height & Channel.
```python
# YOUR CODE HERE
```

#### 3. Display the image using matplotlib imshow().
```python
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

#### 4. Save the image as a PNG file using OpenCV imwrite().
```python

```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
# YOUR CODE HERE
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
# YOUR CODE HERE
```

#### 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
# YOUR CODE HERE
```

#### 8. Resize the image up by a factor of 2x.
```python
# YOUR CODE HERE
```

#### 9. Flip the cropped/resized image horizontally.
```python
# YOUR CODE HERE
```

#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
# YOUR CODE HERE
```

#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN
# YOUR CODE HERE: use putText()
```

#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
rect_color = magenta
# YOUR CODE HERE
```

#### 13. Display the final annotated image.
```python
# YOUR CODE HERE
```

#### 14. Read the image ('Boy.jpg').
```python
# YOUR CODE HERE
```

#### 15. Adjust the brightness of the image.
```python
# Create a matrix of ones (with data type float64)
# matrix_ones = 
# YOUR CODE HERE
```

#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
# YOUR CODE HERE
```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
# YOUR CODE HERE
```

#### 18. Modify the image contrast.
```python
# Create two higher contrast images using the 'scale' option with factors of 1.1 and 1.2 (without overflow fix)
matrix1 = 
matrix2 = 
# img_higher1 = 
# img_higher2 = 
# YOUR CODE HERE
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python
# YOUR CODE HERE
```

#### 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
# YOUR CODE HERE
```

#### 21. Merged the R, G, B , displays along with the original image
```python
# YOUR CODE HERE
```

#### 22. Split the image into the H, S, V components & Display the channels.
```python
# YOUR CODE HERE
```
#### 23. Merged the H, S, V, displays along with original image.
```python
# YOUR CODE HERE
```
Name: MANORAJAPRIYAN.L.E

Register Number: 212225040227

Ex. No. 01

Experiment Title: Image Handling and Pixel Transformations Using OpenCV

```python
import cv2
import matplotlib.pyplot as plt
```

1. Read and display the image ('1.jpg') using OpenCV and Matplotlib.

```python
# Read the image using OpenCV
img = cv2.imread('1.jpg', cv2.IMREAD_COLOR)

# Convert BGR to RGB
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Display the image
plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
```

2. Perform drawing operations on the image.

a) Draw a line from the top-left to the bottom-right of the image.

```python
# Load the image
image = cv2.imread('1.jpg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Get image dimensions
height, width = img_rgb.shape[:2]

# Draw a line from top-left to bottom-right
line_img = cv2.line(
    img_rgb.copy(),
    (0, 0),
    (width - 1, height - 1),
    (255, 0, 0),
    2
)

# Display the image
plt.imshow(line_img)
plt.title("Image with Line")
plt.axis('off')
plt.show()
```

b) Draw a circle at the center of the image.

```python
# Load the image
image = cv2.imread('1.jpg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Get image dimensions
height, width = img_rgb.shape[:2]

# Find the center of the image
center = (width // 2, height // 2)

# Draw a circle at the center
circle_img = cv2.circle(
    img_rgb.copy(),
    center,
    150,
    (0, 255, 0),
    10
)

# Display the image
plt.imshow(circle_img)
plt.title("Image with Circle")
plt.axis('off')
plt.show()
```

c) Draw a rectangle around a specific region of interest in the image.

```python
# Load the image
image = cv2.imread('1.jpg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Draw a rectangle around a region of interest
rectangle_img = cv2.rectangle(
    img_rgb.copy(),
    (50, 50),
    (350, 350),
    (0, 0, 255),
    5
)

# Display the image
plt.imshow(rectangle_img)
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()
```

d) Add the text "OpenCV Drawing" at the top-left corner of the image.

```python
# Load the image
image = cv2.imread('1.jpg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(
    img_rgb.copy(),
    "OpenCV Drawing",
    (10, 30),
    cv2.FONT_HERSHEY_SIMPLEX,
    1,
    (255, 255, 255),
    2
)

# Display the image
plt.imshow(text_img)
plt.title("Image with Text")
plt.axis('off')
plt.show()
```

3. Perform color space conversions.

a) Convert the image from RGB to HSV and display it.

```python
# Load the image
image = cv2.imread('1.jpg')

# Convert BGR to RGB
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

# Display HSV image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()
```

b) Convert the image from RGB to GRAY and display it.

```python
# Convert RGB to Grayscale
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

# Display Grayscale image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
plt.show()
```

c) Convert the image from RGB to YCrCb and display it.

```python
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

# Display YCrCb image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()
```

d) Convert the HSV image back to RGB and display it.

```python
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

# Display the converted RGB image
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
plt.show()
```

4. Perform pixel-level transformations.

a) Access and print the value of the pixel at coordinates (100, 100).

```python
# Load the image
image = cv2.imread('1.jpg')

# Access pixel at coordinates (100, 100)
pixel_value = image[100, 100]

# Print the pixel value
print("Pixel value at (100, 100):", pixel_value)
```

b) Modify the color of the pixel at (200, 200) to white.

```python
# Modify the pixel at (200, 200) to white
image[200, 200] = [255, 255, 255]

# Convert BGR to RGB
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with Modified Pixel")
plt.axis("off")
plt.show()
```

Optional: Modify a 300 × 300 block of pixels to white starting from (200, 200).

```python
# Load the image
image = cv2.imread('1.jpg')

# Modify a 300x300 block to white
image[200:500, 200:500] = [255, 255, 255]

# Convert BGR to RGB
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

5. Resize the original image to half of its size and display it.

```python
# Load the image
image = cv2.imread('1.jpg')

# Get original dimensions
height, width = image.shape[:2]

# Resize the image to half its size
resized_image = cv2.resize(
    image,
    (width // 2, height // 2)
)

# Convert BGR to RGB
resized_image_rgb = cv2.cvtColor(
    resized_image,
    cv2.COLOR_BGR2RGB
)

# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

6. Crop a Region of Interest (ROI) from the image (e.g., a 100 × 100 pixel area starting at (50, 50)) and display it.

```python
# Load the image
image = cv2.imread('1.jpg')

# Crop a 100x100 region starting from (50, 50)
roi = image[50:150, 50:150]

# Convert BGR to RGB
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

# Display the cropped ROI
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

7. Perform image flipping.

a) Flip the original image horizontally and display it.

```python
# Load the image
image = cv2.imread('1.jpg')

# Flip the image horizontally
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB
flipped_horizontally_rgb = cv2.cvtColor(
    flipped_horizontally,
    cv2.COLOR_BGR2RGB
)

# Display horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()
```

b) Flip the original image vertically and display it.

```python
# Flip the image vertically
flipped_vertically = cv2.flip(image, 0)

# Convert BGR to RGB
flipped_vertically_rgb = cv2.cvtColor(
    flipped_vertically,
    cv2.COLOR_BGR2RGB
)

# Display vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
plt.show()
```

8. Save the final modified image to the local directory.

```python
# Load the original image
image = cv2.imread('1.jpg')

# Save the image to the local directory
cv2.imwrite('final_modified_image.jpg', image)

print("Final modified image saved successfully.")
```

Output:

The image was successfully read and displayed. Drawing operations such as line, circle, rectangle, and text were performed. The image was converted into HSV, Grayscale, and YCrCb color spaces. Pixel transformations, resizing, cropping, horizontal and vertical flipping were performed successfully. Finally, the modified image was saved to the local directory.

```
```

## Output:
- **i)** Read and Display an Image.  
- **ii)** Adjust Image Brightness.  
- **iii)** Modify Image Contrast.  
- **iv)** Generate Third Image Using Bitwise Operations.

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

