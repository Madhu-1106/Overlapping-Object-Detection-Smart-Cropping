# Overlapping Object Detection & Smart Cropping  
*A Final-Year AIML Project*

This project focuses on detecting and intelligently cropping the **primary object** in an image, even when multiple objects overlap (for example, a hand partially covering a face).  
It uses a combination of **YOLOv8 segmentation** and **MediaPipe Face Detection** to make better decisions about what to crop.

This is part of my learning in AI/ML, computer vision, and object detection.

---

##  What the System Does

###  Detects all objects in the image using **YOLOv8-Segmentation**  
This gives bounding boxes + segmentation masks.

###  Detects faces using **MediaPipe Face Detection**  
Used to override YOLO when a face is partially covered or misclassified.

###  Identifies the **primary object** using a scoring system based on:
- Object confidence  
- Object type priority (face > person > animals > objects)  
- Object size  
- How central it is in the image  

###  Handles tricky cases like:
- A hand covering a face  
- Overlapping objects  
- Mis-detections  
- Partial occlusions  

### Crops only the most important object  
And optionally uses segmentation masking to create a cleaner cutout.

---

##  Project Structure


Overlapping-Object-Cropping/
│
├ Overlapping.ipynb      # main script
│
├── input img's            # auto-generated output folder
|──output img's
├── README.md
└── requirements.txt

---

##  How to Use (Works in Jupyter & Google Colab)

1. Install dependencies:
   
   pip install -r requirements.txt
   

2. Run your script or notebook.

3. Upload one or more images.

4. The system will:
   - Detect all objects  
   - Pick the most important one  
   - Crop it  
   - Save it inside `cropped_outputs/`

You will also see visualizations such as:
- Bounding boxes (green = final selection)  
- YOLO detections  
- Segmentation preview  
- Cropped final result  

---

##  Why I Built This

In real-world images, objects often overlap — for example:

- A hand covering part of a face  
- People holding objects  
- Pets overlapping with furniture  

To solve this, I combined **deep-learning detection (YOLO)** with **MediaPipe face detection**, and created a custom scoring system to automatically decide the “primary” object.

This project helped me learn:

- Object detection & segmentation  
- MediaPipe pipelines  
- Vision preprocessing  
- Priority-based decision systems  
- Practical AI/ML implementation  

---

## Contributions

This project is learning-oriented.  
Improvements and suggestions are welcome.

---


