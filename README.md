# Count-number-of-Faces-using-Python-OpenCV
The code you provided captures video from the default camera, detects faces in real-time, and draws a rectangle around each face. Additionally, it displays the face number above each face.

1. Libraries Import:
   - `cv2`: OpenCV library used for image processing and working with video frames.
   - `numpy`: A library used for numerical computations (not used explicitly here, but commonly used with OpenCV).
   - `dlib`: A library used for face detection, with the function `get_frontal_face_detector()` for detecting faces.
2. Initialize Video Capture:   - `cap = cv2.VideoCapture(0)`: This opens the webcam (default device 0). If you want to use another camera, you can change the index to `1` or a different number.
3. Face Detector:   - `detector = dlib.get_frontal_face_detector()`: This initializes a pre-trained face detector from `dlib`.
4. Capture Video Frames:
   - Inside the `while` loop, `cap.read()` captures frames continuously.
   - `cv2.flip(frame, 1)` flips the frame horizontally to create a mirror effect.
5. Convert Frame to Grayscale:   - `gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)`: Converts the frame from BGR to grayscale. Face detection typically works better on grayscale images.
6. Face Detection:   - `faces = detector(gray)`: This detects faces in the grayscale image.
7. Face Coordinates:
   - The detected faces are iterated over, and for each face, the coordinates `(x, y)` for the top-left corner and `(x1, y1)` for the bottom-right corner are obtained.
   - `cv2.rectangle(frame, (x, y), (x1, y1), (0, 255, 0), 2)` draws a rectangle around each detected face using the green color (0, 255, 0).
8. Display Face Count:   - A counter `i` is used to keep track of the number of faces detected, and `cv2.putText()` is used to display the face number.
9. Display Frame:   - `cv2.imshow('frame', frame)`: Displays the processed video frame with detected faces.
10.Exit Condition:    - The loop continues until the user presses the "q" key, which triggers the `cv2.waitKey(1) & 0xFF == ord('q')` check.
11.Release and Clean Up:    - `cap.release()` stops the video capture.    - `cv2.destroyAllWindows()` closes all OpenCV windows.
    
Potential Issues & Solutions
- Face detection not working properly**: Ensure that your webcam is functional and that `dlib` and `opencv-python` are properly installed.
- Error in face detection**: If there’s an issue with `dlib` (e.g., installation errors), you can try installing older versions of `dlib` or check system dependencies for building `dlib`.

Required Libraries
As mentioned earlier, the following libraries need to be installed:
```bash
pip install opencv-python numpy dlib
```
Running the Code
Once everything is installed and the code is running, it will continuously detect faces in the webcam feed, drawing rectangles around each face and displaying the face number on the screen. To stop the script, press the "q" key.

This project is just the first step to face recognition with efficient coding using python libraries . If you find  any error in the code  or you have better approach to optimize the code  feel free to contact .
