# 🚀 Space Debris Detection Using YOLOv8

This project demonstrates how to detect **space debris** in video footage using the **YOLOv8 object detection model** from the [Ultralytics](https://github.com/ultralytics/ultralytics) library.

---

## 📂 Project Structure

Space-Debris-Detection/
│
├── best.pt # Trained YOLOv8 model weights
├── detect_video.py # Python script for video inference
├── README.md # Project documentation
├── requirements.txt # Python dependencies
└── sample_video.mp4 # Sample input video (optional)

yaml
Copy
Edit

---

## 📌 Features

- Object detection using YOLOv8
- Frame-by-frame inference on video files
- Real-time display of results using OpenCV
- Easy integration with custom trained models

---

## 📽️ Demo

https://github.com/yourusername/Space-Debris-Detection/assets/demo.gif  
*(Insert a short screen recording or animated GIF of your detection running on video)*

---

## 🧠 Model

The model used is a custom-trained version of **YOLOv8**, trained using [Roboflow](https://roboflow.com/) on a dataset of space debris collisions.

- **Architecture**: YOLOv8n / YOLOv11
- **Framework**: Ultralytics YOLO
- **Training source**: Roboflow dataset `kosmo_v1`
- **Classes**: Space debris, Satellites, Collision events

---

## 🔧 Installation

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/Space-Debris-Detection.git
cd Space-Debris-Detection
2. Create a virtual environment (optional)
bash
Copy
Edit
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
3. Install dependencies
bash
Copy
Edit
pip install -r requirements.txt
If you don't have a requirements.txt yet, you can use:

bash
Copy
Edit
pip install ultralytics opencv-python roboflow
🚀 Usage
1. Place your trained model (best.pt) in the project directory.
2. Place your input video in the same directory or update the path.
3. Run detection:
bash
Copy
Edit
python detect_video.py
You can quit the video window by pressing q.

📄 detect_video.py Explanation
python
Copy
Edit
model = YOLO("best.pt")  # Load model
cap = cv2.VideoCapture("sample_video.mp4")  # Load video

while True:
    ret, frame = cap.read()
    results = model(frame)  # Inference
    annotated = results[0].plot()  # Draw boxes
    cv2.imshow("Object Detection", annotated)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
✅ TODO
 Save output video with bounding boxes

 Deploy on web using Streamlit or Flask

 Train on a larger space dataset

 Benchmark model performance

🤝 Acknowledgements
Ultralytics YOLO

Roboflow

Dataset Credits: Nikita Grigorev's Roboflow dataset

📬 Contact
Rahul Dilla
Email: rahuldilla2002@gmail.com
LinkedIn: linkedin.com/in/rahuldilla

🛡️ License
This project is licensed under the MIT License - see the LICENSE file for details.

yaml
Copy
Edit

---

### 📌 Tip:
- Rename the repo to something like `space-debris-detection-yolo` on GitHub.
- Add a `requirements.txt` file if you haven't already:
```txt
ultralytics
opencv-python
roboflow
