# ⚽ Object Tracking with YOLOv11 & Kalman Filter

A lightweight real-time system for tracking soccer ball movement in broadcast footage using a Kalman Filter and YOLOv11. Designed for handling partial occlusions, missed detections, and camera motion using confidence-aware prediction.

---


## 🧑‍💻 Author

⚽ Built with Football Love on highly Caffeinated Code Sessions ☕  


---


## 🎬 Example Output Video


[![Watch the demo](assets/1.jpg)](https://drive.google.com/file/d/1-N3WGmM-LseNHS0ktyKw9eAOg_5pyGdG/view?usp=sharing)



---

## 🎯 Project Goals

- Detect soccer ball, players, goalkeepers, and referees in match footage.
- Predict the ball’s position even when occluded or not detected.
- Compare predicted vs. actual positions using error metrics.

---

## 🚀 Technologies Used

- `YOLOv11` (via Ultralytics) for detection  
- `Kalman Filter` (`pykalman`) for trajectory tracking  
- `Supervision` for annotated video rendering  
- `Roboflow` for model hosting  
- `ONNX Runtime` GPU acceleration on Colab  

---

## 🧪 Workflow Overview

1. 🔍 **Detection**  
   YOLOv11 detects objects in each video frame (ball, players, etc.).

2. 📈 **Tracking**  
   A Kalman Filter smooths and predicts ball positions based on confidence scores.

3. 🎥 **Visualization**  
   Annotated video is generated with actual vs. predicted positions.

4. 📊 **Evaluation**  
   Errors (mean, RMSE, max) between prediction and ground truth are visualized and stored.

---

## 🧠 Kalman Filter Model

Tracks `[x, y, vx, vy, ax, ay]` using a constant acceleration model:

```
state = [position_x, position_y, velocity_x, velocity_y, acceleration_x, acceleration_y]
```

---

## 🖼️ Sample Output

| Annotated Detection | Kalman Prediction       | CSV Logging              |
|---------------------|-------------------------|---------------------------|
| ✅ Players & Ball    | ✅ Predicted Trajectory | ✅ Saved as `positions.csv` |

---

## 📁 Directory Structure

```
Object-Tracking-EKF-YOLO/
├── track_ball.py
├── kalman_filter.py
├── yolov11_training.ipynb
├── inference.ipynb
├── vids/
│   ├── 121364_0.mp4
│   └── 121364_0_result_1.mp4
└── positions.csv
```

---

## 📝 Citation / Credits

- YOLOv11 via [Ultralytics](https://github.com/ultralytics/ultralytics)
- Roboflow dataset: `football-players-detection-3zvbc`
- `Supervision` library for annotations

---


