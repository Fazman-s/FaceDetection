# FaceDetection
Face and Eye Detection Using openCV:
The provided code is used for real-time face detection using the Haar cascade classifier in OpenCV. Here's a breakdown of how the code works:

1. Importing libraries: The code first imports the necessary libraries, including `numpy` for numerical operations and `cv2` (OpenCV) for computer vision tasks.

2. Setting up video capture: The code initializes a video capture object using `cv2.VideoCapture(0)`, which captures video from the default camera (index 0).

3. Loading cascade classifiers: The code loads two Haar cascade classifiers using `cv2.CascadeClassifier`. These classifiers are XML files that contain pre-trained models for detecting faces and eyes. The file paths `haarcascade_frontalface_default.xml` and `haarcascade_eye.xml` are provided, and `cv2.data.haarcascades` is a predefined path in OpenCV where these classifiers are stored.

4. Face detection loop: The code enters a continuous loop to perform face detection on each frame of the captured video. The loop runs until the user presses the 'q' key.

5. Reading the frame: Inside the loop, `cap.read()` retrieves the current frame from the video capture.

6. Converting to grayscale: The frame is converted to grayscale using `cv2.cvtColor()` since the Haar cascade classifiers work on grayscale images.

7. Face detection: The `face_cascade.detectMultiScale()` method is applied to the grayscale frame to detect faces. It returns a list of rectangles representing the detected faces.

8. Face and eye bounding boxes: For each detected face, a rectangle is drawn using `cv2.rectangle()` on the original color frame. The coordinates of the rectangle are obtained from the detected face's bounding box.

9. Eye detection: Within each detected face region, the `eye_cascade.detectMultiScale()` method is used to detect eyes. It returns a list of rectangles representing the detected eyes.

10. Eye bounding boxes: For each detected eye, a rectangle is drawn using `cv2.rectangle()` on the face region.

11. Displaying the frame: The modified frame with bounding boxes is displayed using `cv2.imshow()`.

12. Exiting the loop: If the user presses the 'q' key (detected by `cv2.waitKey(1) == ord('q')`), the loop is exited.

13. Releasing resources: After exiting the loop, the video capture is released using `cap.release()`, and all OpenCV windows are closed using `cv2.destroyAllWindows()`.

Overall, this code continuously captures video from the default camera, detects faces and eyes in real-time using Haar cascade classifiers, and displays the video stream with bounding boxes around detected faces and eyes.
