# Real-Time-Image-Capture-Python
#Python #OpenCV #WebcamCapture #ComputerVision #OpenSource #ImageProcessing #RealTimeCapture  
For those who are using this code on Google colab they can Try this trick :-(
To capture an image when a button is pressed or when the letter "m" is pressed, you can use the Python library OpenCV, 
which provides functionalities for capturing images from a camera. Additionally, you can use the keyboard library to detect key presses.
Before running the code, make sure you have both opencv-python and keyboard installed. You can install them using pip:



    Go to Google Colaboratory

    Create a new notebook

    Click snippet panel

    Click Camera Capture. Click insert

    Run script: Shift + Enter


!pip install opencv-python
!pip install keyboard

Here's the Python code to capture an image when a button is pressed or when the letter "m" is pressed:

import cv2
import keyboard

def capture_image():
    # Open the camera
    cap = cv2.VideoCapture(0)

    # Check if the camera is opened successfully
    if not cap.isOpened():
        print("Error: Could not open the camera")
        return

    while True:
        # Capture frame-by-frame
        ret, frame = cap.read()

        # Display the frame
        cv2.imshow("Press 'm' to capture, Press 'q' to quit", frame)

        # Check for key presses
        if cv2.waitKey(1) & 0xFF == ord('m'):
            # Save the captured frame as an image
            cv2.imwrite("captured_image.png", frame)
            print("Image captured successfully!")
        elif cv2.waitKey(1) & 0xFF == ord('q'):
            break

    # Release the camera and close all windows
    cap.release()
    cv2.destroyAllWindows()

if __name__ == "__main__":
    print("Press 'm' to capture an image, Press 'q' to quit")
    capture_image()
