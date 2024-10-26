# License-Plate-Detection-and-Recognition-using-YOLOv8-and-OCR

# Project: License Plate Detection and Recognition using YOLOv8 and OCR

## Problem Understanding
As a Data Scientist, it's common to encounter data that is not always in the desired format. In this case, the data was in the form of images or videos, containing license plates. The task was to detect these license plates and extract their text information. This required multiple stages:

1. **Data Annotation**: Labeling the data to mark the license plates in the images by drawing bounding boxes.
2. **Data Conversion**: Converting these annotations into the YOLO format for model training.
3. **Model Training**: Training a YOLOv8 model using the labeled data to detect license plates.
4. **License Plate Extraction**: Extracting the detected license plate numbers from video data using Optical Character Recognition (OCR).

## Steps Involved

### 1. Data Annotation
- The first step was to prepare the dataset. I manually labeled the images by drawing bounding boxes around the license plates and converted the annotations into YOLO format (which involves `.txt` files specifying the coordinates of the bounding boxes).
  
### 2. Model Training
- Using the annotated dataset, I trained the YOLOv8 model. The YOLO (You Only Look Once) model is highly efficient for object detection tasks. It was chosen for its speed and accuracy, which are critical for real-time license plate detection.
  
- After training the model on the prepared dataset, I obtained a custom-trained YOLO model specifically designed to detect license plates.

### 3. License Plate Detection from Video
- With the trained model, I processed video data frame by frame to draw bounding boxes around detected license plates. This allowed me to visualize where the license plates were in the video and track them.

### 4. License Plate Number Extraction using OCR
- To extract the text of the license plates, I used **Tesseract OCR**. By applying Optical Character Recognition (OCR) on the detected license plate regions, I was able to extract the license plate numbers.

- Preprocessing was added to the detected regions for better OCR accuracy. This included converting the region to grayscale and applying thresholding.

### 5. Improving Recall
- I fine-tuned the detection and OCR extraction process to improve recall, ensuring that most of the license plates in the video were successfully detected and extracted.

## Results and Key Improvements
- After training the YOLOv8 model and integrating OCR, the recall (the ability to detect most true license plates) improved significantly.
- Deduplication logic was applied to avoid counting the same plate multiple times, which further refined the results.
  
## Code Implementation

### Steps to Run:
1. Upload your video file using the `files.upload()` function in Google Colab.
2. Use the trained YOLOv8 model (`best_license_plate_model.pt`) to detect license plates in the video.
3. Use the OCR (Tesseract) to extract the text from the detected license plate regions.
4. Deduplicate the extracted license plates to avoid counting the same plate multiple times.
5. The output video with bounding boxes will be saved, and the extracted license plate numbers will be stored in a CSV file.




