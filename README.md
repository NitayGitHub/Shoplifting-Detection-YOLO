# Shoplifting Detection YOLOv8
## **Introduction**
Shoplifting poses a significant challenge for retailers, leading to substantial financial losses and compromised store security. To combat this, the integration of cutting-edge computer vision techniques in surveillance systems has become essential. YOLOv8 (You Only Look Once) represents a major advancement in object detection models, offering fast detection and classification results in real time.

Project Goal: Identify suspicious behavior and detect potential shoplifting incidents.

## **Installation**
This project is run on Kaggle instead of Google Colab. Before running the code, ensure that the following libraries are pre-installed:

- **Torch**: For deep learning support and model training.
- **Ultralytics**: To leverage YOLOv8 models for object detection.
- **OpenCV (cv2)**: For image and video processing.
- **Yaml**: For reading and writing configuration files.
- **Matplotlib**: For visualizing results and plots.

To install these libraries, you can use the following command:

```python
!pip install torch ultralytics opencv-python-headless pyyaml matplotlib
```

## **Data Sources**

The images and labels for this project were downloaded from [Roboflow](https://universe.roboflow.com/roaya-nj7sb/shoplift). The dataset includes four labeled classes:

- **Empty Hands**: Detecting individuals without any items in hand.
- **Dropping**: Actions where items are dropped or discarded.
- **Picking/Holding**: Detecting when individuals pick up or hold items.
- **Shoplifting**: Identifying suspicious activities such as hiding or stealing items.

By leveraging these annotated classes, the model is designed to accurately identify and differentiate between normal shopping activities and potentially harmful behaviors.

Train set: 2374 images (80.91%) of total

Valid set: 560 images (19.09%) of total

![image](https://github.com/user-attachments/assets/4889920f-b273-4388-93e3-76843c7a025d)

## **Training Results**

| Class          | Images | Instances | Precision | Recall | mAP50 | mAP50-95 |
|----------------|--------|-----------|-----------|--------|---------|--------------|
| **All**        | 560    | 868       | 0.726     | 0.653  | 0.696   | 0.285        |
| **EmptyHands** | 230    | 386       | 0.772     | 0.699  | 0.748   | 0.304        |
| **Dropping**   | 44     | 44        | 0.633     | 0.432  | 0.480   | 0.138        |
| **Picking/Hold** | 146  | 173       | 0.712     | 0.613  | 0.672   | 0.300        |
| **Shoplifting** | 263   | 265       | 0.786     | 0.868  | 0.885   | 0.400        |

![image](https://github.com/user-attachments/assets/a27726a8-dd88-4b72-ae47-1dad7c7e5c79)


## **Conclusion**

Most of the results are considered good, with high precision and recall values across the majority of classes. However, the **"Dropping"** class exhibits lower recall and mAP50, which suggests that the model struggles more with detecting this behavior. This could be due to the smaller number of images in this class compared to the others. Future work could include adding more images to the **"Dropping"** class.



