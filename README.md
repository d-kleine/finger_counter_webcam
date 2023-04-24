# Finger counter with OpenCV and MediaPipe

This is a simple finger counter program that uses OpenCV and MediaPipe to detect hand landmarks and count the number of fingers that are extended.

The program displays the camera feed with the detected hand landmarks and the finger count. The finger count is updated in real-time as the user changes the number of fingers that are extended.

**Installation**

To run this program, you need to install the following dependencies:
* OpenCV (version 4.5 or later)
* MediaPipe (version 0.8.7 or later)

You can install these dependencies using pip:
`pip install opencv-python mediapipe`

**How it works**

The program works by using MediaPipe to detect the landmarks of the user's hand, and then counting the number of fingers that are extended based on the positions of these landmarks.

The program assumes that the user is holding their hand in front of the camera, with their palm facing downwards. It detects the landmarks of the user's hand using MediaPipe, and then checks the position of the thumb and each finger to determine whether it is extended or not.

The finger counting in this program is done by detecting the position of the landmarks for each finger and determining whether they are open or closed.

The program looks for the following five landmarks for each finger:

    The tip of the finger (landmark id: 4, 8, 12, 16, 20)
    The base of the finger (landmark id: 3, 7, 11, 15, 19)
    The middle joint of the finger (landmark id: 2, 6, 10, 14, 18)
    The proximal joint of the finger (landmark id: 1, 5, 9, 13, 17)
    The metacarpal bone of the finger (landmark id: 0)

See <a href="https://developers.google.com/mediapipe/solutions/vision/hand_landmarker#models">here</a> for further information.

The program uses the position of the tip and base landmarks to determine whether the finger is open or closed. For the thumb, the program looks at the position of the tip and proximal joint landmarks instead.

If the distance between the tip and base landmarks is greater than a certain threshold, the finger is considered to be open. Otherwise, the finger is considered to be closed.

The finger counting code in the program looks for the open or closed state of each finger and updates the finger count accordingly. The finger count is then displayed on the camera feed in real-time, allowing the user to see how many fingers they are extending.

**Credits**

It uses the following libraries:

    OpenCV - https://opencv.org/
    MediaPipe - https://developers.google.com/mediapipe

The program is based on the MediaPipe Hands solution, which is developed by Google. You can learn more about this solution on the MediaPipe website:

    MediaPipe Hands - https://developers.google.com/mediapipe/solutions/vision/hand_landmarker