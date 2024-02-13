#python 
#opencv

```python
import cv2
import numpy as np
import math

# Turn on the Camera
cam = cv2.VideoCapture(0)

while True:
    # Get camera frame by frame
    ret, frame = cam.read()

    # Flip the frame vertically
    # 1 means flip about the y axis
    frame = cv2.flip(frame, 1)

    # Making a frame
    # cv2.rectangle(frame, (300,200), (600,500), (255,0,0), 5)

    # Cutting the image
    crop_img = frame[50:350, 350:650]

    # Turning to grayscale
    gray = cv2.cvtColor(crop_img, cv2.COLOR_BGR2GRAY)

    # Blurring image with kernel blurring
    blur = cv2.GaussianBlur(gray, (35,35), 0)

    # Thresholding
    ret, thresh = cv2.threshold(blur, 0, 255, cv2.THRESH_BINARY_INV + cv2.THRESH_OTSU)

    # Contours
    try:
        contours, hierarchy = cv2.findContours(thresh, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)
        cnt = max(contours, key = lambda x : cv2.contourArea(x))
    except ValueError:
        continue
    cv2.drawContours(crop_img, [cnt], 0, (0,255,0), 3)

    # Convex Hull?
    # Return points set to False to only return the indices of the contour points that are in the convex hull
    hull = cv2.convexHull(cnt, returnPoints=False)
    # cv2.drawContours(crop_img, [hull], 0, (0,255,0), 3)
    
    # Initialize finger count
    nFingers = 1

    # Convexity defects
    # Uses original contour and convexity hull
    # Returns Array like [[[s1, e1, f1, d1]], [[s2, e2, f2, d2]]] of index of point in contour
    defects = cv2.convexityDefects(cnt,hull)
    if defects is None:
        continue
    for index in range(defects.shape[0]):
        s, e, f, d = defects[index,0]
        start = tuple(cnt[s][0])
        end = tuple(cnt[e][0])
        far = tuple(cnt[f][0])
        
        # Find angle of Start-Far-End
        # Formula find distance two coordinates: squareroot((y1-y2)^2 + (x1-x2)^2)
        startToFar = math.sqrt((start[0]-far[0])**2 + (start[1]-far[1])**2)
        endToFar = math.sqrt((end[0]-far[0])**2 + (end[1]-far[1])**2)
        startToEnd = math.sqrt((start[0]-end[0])**2 + (start[1]-end[1])**2)

        # Formula find angle from sides: cos^-1((a^2+b^2-c^2)/(2ab))
        angle = math.acos((startToFar**2+endToFar**2-startToEnd**2)/(2*startToFar*endToFar))

        # Display convex hull as lines
        cv2.line(crop_img, start, end, (0,255,0), 3)

        if angle <= math.pi/2:
            # Display Far points as circles
            cv2.circle(crop_img, far, 5, (0,0,255), -1)
            nFingers += 1

    cv2.putText(crop_img, str(nFingers), (20, 50), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 0, 0), 2, cv2.LINE_AA)

    # Display video feed
    # cv2.imshow('raw',frame)
    # cv2.imshow('Blurred', blur)
    # cv2.imshow('Cropped', thresh)
    cv2.imshow('Contours', crop_img)

    # Quit application when 'q' key is pressed
    key = cv2.waitKey(1)
    if key == ord('q'):
        break

# cropped = crop_img[-1]
# print(cropped)

# Switch off camera
# and close all open windows
cam.release()
cv2.destroyAllWindows()
```


```python
import cv2
import mediapipe as mp

cam = cv2.VideoCapture(0)

mp_drawing = mp.solutions.drawing_utils
mp_drawing_styles = mp.solutions.drawing_styles
mp_hands = mp.solutions.hands
hands = mp_hands.Hands(model_complexity = 0,
                       min_detection_confidence = 0.5,
                       min_tracking_confidence = 0.5)

while True:
    ret, frame = cam.read()
    frame = cv2.flip(frame, 1)

    # Process image to obtain hand landmarks
    frame.flags.writeable = False
    frame = cv2.cvtColor(frame,cv2.COLOR_BGR2RGB)
    results = hands.process(frame)
    
    frame.flags.writeable = True
    frame = cv2.cvtColor(frame,cv2.COLOR_RGB2BGR)

    if results.multi_hand_landmarks:
        for hand_landmark in results.multi_hand_landmarks:  
            # Draw the hand landmark Points
            mp_drawing.draw_landmarks(
                frame,
                hand_landmark,
                mp_hands.HAND_CONNECTIONS,
                mp_drawing_styles.get_default_hand_landmarks_style(),
                mp_drawing_styles.get_default_hand_connections_style()
            )

        hand_index = results.multi_hand_landmarks.index(hand_landmark)
        hand_label = results.multi_handedness[hand_index].classification[0].label

        hand_landmark_pos = []
        for landmark in hand_landmark.landmark:
            hand_landmark_pos.append([landmark.x, landmark.y])
            
        nFingers = 0  

        if hand_label == 'Left':
            cv2.putText(frame, 'LEFT', (20, 100), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 0, 0), 2, cv2.LINE_AA)
        elif hand_label == 'Right':
            cv2.putText(frame, 'RIGHT', (20, 100), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 0, 0), 2, cv2.LINE_AA)


        if hand_label == "Left" and hand_landmark_pos[4][0] > hand_landmark_pos[3][0]:
            nFingers += 1
        elif hand_label == "Right" and hand_landmark_pos[4][0] < hand_landmark_pos[3][0]:
            nFingers += 1

        # if hand_landmark_pos[4][0] > hand_landmark_pos[3][0]:
        #     nFingers += 1

        if hand_landmark_pos[8][1] < hand_landmark_pos[6][1]:
            nFingers += 1
        if hand_landmark_pos[12][1] < hand_landmark_pos[10][1]:
            nFingers += 1
        if hand_landmark_pos[16][1] < hand_landmark_pos[14][1]:
            nFingers += 1
        if hand_landmark_pos[20][1] < hand_landmark_pos[18][1]:
            nFingers += 1
            
        cv2.putText(frame, str(nFingers), (20, 50), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 0, 0), 2, cv2.LINE_AA)

    cv2.imshow('frame', frame)
    key = cv2.waitKey(1)
    if key == ord('q'):
        break
```