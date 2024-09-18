# DEfDO: Distance Estimation for Detected Objects

#### DEfDO is a real-time distance estimation system designed for mobile devices. By leveraging object detection through a pre-trained YOLOv8n model and depth estimation using a pre-trained ZoeDepth model, DEfDO enables accurate distance measurements of detected objects directly on a mobile app.


 ## Table of Contents
 - [Key Features](#key-features)
 - [Model Selection](#model-selection)
 - [Data Collection](#data-collection)
 - [Preprocessing](#preprocessing)
 - [Data Augmentation](#data-augmentation)
 - [Mobile App Integration](#mobile-app-integration)
 - [Performance Evaluation](#performance-evaluation)


 ## Key Features
 - **Object Detection:** Real-time detection of objects using the YOLOv8n model.
 - **Distance Estimation:** Metric depth estimation using ZoeDepth for direct distance measurements.
 - **Optimized for Mobile:** Designed for real-time performance on mobile devices.
 - **User-Friendly Interface:** Seamless integration into mobile app environments.


 ## Model Selection
 - **YOLOv8n:** 
   - Selected for its balance between speed and accuracy, ideal for real-time applications.
   - The YOLOv8n model has been fine-tuned to detect only four specific classes: cars, persons, traffic lights, and vehicle plates.
 - **ZoeDepth:**
   - Chosen for its capability to provide metric depth estimation, which allows direct object distance measurements without additional post-processing.


 ## Data Collection
- **COCO Dataset:** Utilized the FiftyOne library API to access and process the COCO dataset.
- **Kaggle:** Sourced additional training data from Kaggle.
- **Roboflow:** Leveraged Roboflow for image labeling and data augmentation.

 ## Preprocessing
 - **Resizing:** Images were resized to a consistent size to ensure compatibility with the models.
- **Normalization:** Image pixel values were normalized to a specific range (e.g., 0-1) for efficient processing.
- **Auto-Orientation:** Images were automatically rotated to ensure correct orientation.
- **Contrast Stretching:** Contrast was adjusted using contrast stretching to improve image quality.

 ## Data Augmentation
 - **Shear:** Images were sheared horizontally and vertically by ±13° and ±12°, respectively.
- **Brightness:** Brightness was adjusted by between -15% and +15%.
- **Blur:** Images were blurred up to 1.7 pixels.
- **Noise:** Up to 1.56% of pixels were added as noise.


 ## Mobile App Integration
 - **Object Detection:**
   - The app was initially designed for a TFLite detection model, making the integration of YOLOv8n straightforward.
 - **Depth Estimation:**
   - The app requires customization to incorporate the ZoeDepth model via TFLite and display real-time distance estimates for detected objects.


 ## Performance Evaluation
 - **Object Detection:**
   - Evaluated using standard metrics such as AP, recall, and precision.
 - **Depth Estimation:**
   - Performance is measured by Root Mean Squared Error (RMSE) and Relative Absolute Error (RAE) to gauge accuracy.

 ## Future Work

 - **Accuracy Improvement:** Explore techniques to further enhance the accuracy of both object detection and depth estimation.
 - **Performance Optimization:** Optimize the mobile app for even faster inference times, especially on lower-end devices.