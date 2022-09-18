import cv2
import numpy as np

def empty(x):
  pass

cv2.namedWindow("HSV Color Space")
cv2.resizeWindow("HSV Color Space", 300,300)

cv2.createTrackbar("H Min", "HSV Color Space", 0, 255, empty)
cv2.createTrackbar("H Max", "HSV Color Space", 255, 255, empty)
cv2.createTrackbar("S Max", "HSV Color Space", 0, 255, empty)
cv2.createTrackbar("S Min", "HSV Color Space", 255, 255, empty)
cv2.createTrackbar("V Max", "HSV Color Space", 0, 255, empty)
cv2.createTrackbar("V Min", "HSV Color Space", 255, 255, empty)

video = cv2.VideoCapture(0)

while True:
  ret, frame_stored = video.read() 
  
  img_hsv = cv2.cvtColor(frame_stored, cv2.COLOR_BGR2HSV)
  
  h_min = cv2.getTrackbar("H Min", "HSV Color Space")
  h_mam = cv2.getTrackbar("H Min", "HSV Color Space")
  s_min = cv2.getTrackbar("S Min", "HSV Color Space")
  s_max = cv2.getTrackbar("S Max", "HSV Color Space")
  v_min = cv2.getTrackbar("V Min", "HSV Color Space")
  v_max = cv2.getTrackbar("V Max", "HSV Color Space")
  
  lower = np.array([h_min, s_min, v_min])
  upper = np.array([h_max, s_max, v_max])
  
  mask = cv2.inRange(img_hsv, lower, upper)
  segmentation = cv2.bitwise_and(frame_stored, frame_stored, mask = mask)
  
  cv2.imshow("Result", segmentation)
  
  if cv2.waitKey(30) & 0xFF == ord("q"): 
    break
