# 🧍 Human Motion Recognition System

This project focuses on **real-time human motion recognition** using **OpenCV**, **MediaPipe**, and deep learning-based models. It also includes integration with **Unity** to visualize recognized movements on a 3D character model.

---

## 🔥 Project Highlights

- 🎥 Detect human movement in real-time from webcam or video.
- 🧠 Recognize specific actions using CNN + LSTM-based models.
- 🧍‍♂️ Map motion points to a 3D character in Unity.
- 🧾 Export motion points as `.txt` or `.csv` for later animation use.
- 🧩 Modular architecture for dataset creation, training, prediction, and visualization.

---

## 📁 Folder Structure

Motion_Recognition/
│
├── dataset/ # Custom dataset for training/testing (CSV, TXT)
├── models/ # Trained model weights (CNN + LSTM, etc.)
├── scripts/ # Python files for motion detection and recognition
│ ├── capture_points.py # Capture pose landmarks from video
│ ├── recognize_action.py # Predict action using trained model
│ ├── export_to_txt.py # Export landmarks to text file
│ └── preprocess_data.py # Format data for training
├── unity_integration/ # Unity project and scripts
│ ├── Assets/ # Unity assets including 3D model
│ └── AnimateFromText.cs # C# script to map motion to model
├── sample_videos/ # Sample video files for testing
├── outputs/ # Output pose overlays and predictions
└── README.md # You are here!


---

## 🛠️ Technologies Used

| Technology   | Purpose                                  |
|--------------|-------------------------------------------|
| Python       | Backend motion processing                |
| OpenCV       | Video capture & image processing         |
| MediaPipe    | Real-time pose estimation                |
| TensorFlow/Keras or PyTorch | Deep learning model for motion classification |
| Unity        | 3D character animation                   |
| C#           | Used for scripting Unity character bone movement |

---

## 🧠 How It Works

### Step 1: Pose Detection
- Use **MediaPipe** to detect 33 body landmarks from each frame.
- Store these coordinates over time to represent movement.

### Step 2: Action Recognition
- Feed pose sequences (x, y, z coordinates) into a **CNN + LSTM** model.
- Model predicts the action label: e.g., walking, waving, jumping, etc.

### Step 3: Export for Unity
- Export sequences to `.txt` format.
- The Unity script reads this file and maps points to a 3D character's bones.

### Step 4: Visualize in Unity
- Animate a rigged character using the input motion file.
- Supports step-by-step playback of movements.

---

## 🔧 Setup Instructions

### 1. Clone the Repository
```bash

git clone https://github.com/Pavithran030/Motion_Recognition.git
cd Motion_Recognition

```

### 2. Create a Python Virtual Environment

```bash

- python -m venv venv

```
- source venv/bin/activate    # On Windows: venv\Scripts\activate

### 3. Install Dependencies

- pip install -r requirements.txt

### 4. Run the Motion Capture Script

- python scripts/capture_points.py

### 5. Recognize the Action (Optional)

- python scripts/recognize_action.py

### 🕹 Unity Integration Guide
Steps:
- Open the unity_integration folder in Unity.

- Place your .txt motion data file in the Resources folder.

- Attach the AnimateFromText.cs script to your character object.

- Configure bone mapping in the script (e.g., head = "Head", left arm = "LeftArm").

- Hit Play to view the animation based on your motion file.

### 🧪 Model Training (Optional)

- If you want to train your own model:

- Collect motion sequences and export them from videos.

- Run scripts/preprocess_data.py to prepare the dataset.

- Build a CNN + LSTM model (template coming soon).

Train using TensorFlow or PyTorch.

Save the model to the models/ folder.
