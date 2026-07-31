## EXP 2

## Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file.
2. Display the video.
3. Display the video by resizing the window.
4. Rotate and display the video.

---

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook
- OpenCV (`cv2`)
- Matplotlib

---

## Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture a frame from the webcam and save it as a JPG image.

### Step 3:
Display the captured image using Matplotlib.

### Step 4:
Capture and display the live webcam video continuously.

### Step 5:
Resize the captured video frames and display them.

### Step 6:
Rotate the captured video frames by 90° clockwise and display them.

---

## Program

### Developed By: **KIRAN  MP** 

### Register No: **212224230123**

---

### 1. Import the required libraries.

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```

---

### 2. Capture a frame from the webcam and save it as a JPG image.

```python
cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()
```

---

### 3. Read the captured image.

```python
captured_image = cv2.imread("captured_frame.jpg")
```

---

### 4. Display the captured image.

```python
plt.imshow(captured_image[:, :, ::-1])
plt.title("Captured Frame")
plt.axis("off")
plt.show()
```

---

### 5. Display the live webcam video.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

### 6. Display the video after resizing.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

### 7. Rotate the video by 90° clockwise and display it.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

## Output

### i) Write the frame as JPG image
The captured frame is saved as **captured_frame.jpg**.

<img width="625" height="507" alt="image" src="https://github.com/user-attachments/assets/65d83ac7-8b65-45b2-b408-3f7e438f2d37" />


### ii) Display the video
The live webcam video is displayed.

<img width="622" height="467" alt="image" src="https://github.com/user-attachments/assets/41511ada-5f53-46a4-b426-e347f425851f" />

### iii) Display the video by resizing the window
The webcam video is displayed after resizing the frame.

<img width="622" height="467" alt="image" src="https://github.com/user-attachments/assets/bf320bd1-0aa1-4297-9899-43e95778cafc" />


### iv) Rotate and display the video
The webcam video is displayed after rotating it by **90° clockwise**.

<img width="351" height="465" alt="image" src="https://github.com/user-attachments/assets/350c0bb9-4db0-4dfa-aafd-124f8b745154" />

## Result

Thus, the image was successfully captured from the webcam and various video processing operations such as image capture, live video display, resizing, and rotation were performed successfully using OpenCV.
