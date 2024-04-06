# Loitering Detection
Loitering detection" refers to technology or methods used to identify people who are lingering or spending an unusual amount of time in a particular area. It helps in detecting suspicious behaviour or potential security threats in public spaces or private properties.
- It's a security technique that spots suspicious behaviour in an area.
- It works by triggering alerts when someone is having suspicious behaviour for too long, and also it notes down the Date and Time and Captures the Image.
- This helps enhance security in places like Stores, Transport, Public Places, etc.

---
### STEPS : 
1. Read the video file using OpenCV's VideoCapture function.
2. Load the YOLO object detection model using the provided weight file "yolov8l.pt".
3. Define a list classNames containing class names such as 'person', 'bicycle', 'car', etc.
4. Initialize a SORT tracker object with parameters (max_age, min_hits, and iou_threshold).
5. Create empty dictionaries to store tracker data, captured frames, and loitering status.
6. Start an infinite loop to process each frame of the video:
    - Read a frame from the video capture.
    - Resize the frame to (640, 480) using cv2.resize() if necessary.
    - Detect objects in the frame using the YOLO model and enable streaming display.
    - Extract object information from the detection results and store it in an array "detections".
    - Update the SORT tracker with the new bounding box coordinates / information.
    - Process each tracked object:
      - Draw bounding boxes and display their IDs on the frame for tracked objects.
      - Update the object's traced path and draw lines to visualize the path of tracked objects.
      - Calculate and display the object's variance to detect potential loitering behaviour.
    - Capture frames and display warning text if loitering is detected.
    - Display the processed frame with detected objects and tracked paths.
Exit the loop if 'q' is pressed.
7. Release the video capture and close OpenCV windows.

---
#### SORT (Simple Online and RealTime Tracking)
- SORT is a method that assigns unique IDs to objects, tracking them across video frames in real-time, even when temporarily lost from view. 
- SORT is invaluable for real-time object tracking in various applications like surveillance, self-driving cars, and sports analysis, where monitoring multiple objects' movements over time is essential.
- Check out the SORT algorithm on GitHub at: https://github.com/abewley/sort.
