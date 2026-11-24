# YOLOv8 Object Detection and Tracking

This project uses YOLOv8 to detect and track three custom object classes: eraser, glue stick, and lint roller.

The dataset consists of 320 images collected through direct photography. The images were annotated using Roboflow, and the model was trained using Google Colab.

## 1. Dataset

| Class | Number of Images |
|---|---:|
| Eraser | 120 |
| Glue Stick | 100 |
| Lint Roller | 100 |
| **Total** | **320** |

- Annotation Tool: Roboflow
- Annotation Method: Manual and AI-assisted labeling
- Dataset Split: Train 70% / Validation 20% / Test 10%
- Image Size: 640 × 640

## 2. Model Training

The YOLOv8n model was trained using the Ultralytics library in Google Colab.

| Parameter | Setting |
|---|---|
| Model | YOLOv8n |
| Epochs | 50 |
| Batch Size | 8 |
| Image Size | 640 |
| GPU | NVIDIA Tesla T4 |
| Number of Classes | 3 |

## 3. Model Performance

The trained model achieved the following results on the validation dataset.

| Class | Precision | Recall | mAP@50 | mAP@50:95 |
|---|---:|---:|---:|---:|
| Eraser | 0.957 | 0.800 | 0.881 | 0.778 |
| Glue Stick | 1.000 | 0.997 | 0.995 | 0.848 |
| Lint Roller | 0.847 | 0.831 | 0.905 | 0.726 |
| **Overall** | **0.935** | **0.876** | **0.927** | **0.784** |

## 4. Object Detection and Tracking

The trained YOLOv8n model was applied to a video containing all three object classes.

Object tracking was performed using the Ultralytics `track()` method. The output video includes bounding boxes, class labels, tracking IDs, and movement trajectories.

A 5-second object detection and tracking video was generated.

Some detection failures and tracking ID changes occurred, particularly for the eraser and lint roller.

## 5. Repository Files

| File | Description |
|---|---|
| `final_3class_best.pt` | Trained YOLOv8n model weights |
| `tracking_result.mp4` | 5-second object detection and tracking video |
| `training.ipynb` | Google Colab notebook used for training and experimentation |
| `trajectory.csv` | Recorded object tracking coordinates and IDs |

## 6. Tools and Libraries

- Python
- Ultralytics YOLOv8
- Google Colab
- Roboflow
- OpenCV

## 7. References

- [Ultralytics GitHub Repository](https://github.com/ultralytics/ultralytics)
- [Ultralytics Training Documentation](https://docs.ultralytics.com/modes/train/)
- [Ultralytics Tracking Documentation](https://docs.ultralytics.com/modes/track/)
