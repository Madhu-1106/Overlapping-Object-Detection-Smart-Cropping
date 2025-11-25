# Overlapping-Object-Detection-Smart-Cropping
This project detects multiple objects in an image and automatically identifies the primary object, even when objects overlap or partially occlude one another. It uses YOLOv8 Segmentation for object detection and MediaPipe Face Detection for accurate prioritization when faces are present.

 Features
* YOLOv8 Segmentation
  Detects all objects
  Provides bounding boxes + segmentation masks

* MediaPipe Face Detection
  Identifies faces with high accuracy
  Overrides YOLO decisions when a face is partially hidden or overlapped

* Smart Primary Object Selection
  Scores objects using:
  Detection confidence
  Object category priority (face > person > animals > others)
  Object size
  Center position in the image

* Handles Complex Scenarios
  Face covered by hand
  Multiple people
  Overlapping objects
  Misclassifications
  Partial occlusion

* Smart Cropping
  Crops only the final selected object
  Optionally uses segmentation mask for cleaner cutouts

--- Installation
1. Install dependencies
pip install -r requirements.txt

2. Install YOLOv8
pip install ultralytics

--- Run Instructions
For Jupyter Notebook
jupyter notebook Overlapping.ipynb

--Inside the Notebook:
Upload images into input img's/
Run all cells
YOLO + MediaPipe will:
Detect all objects
Pick the primary object
Crop it
Save it into output img's/

-- You will also see:
YOLO detections
Segmentation overlays
Final selection bounding box
Cropped output preview
