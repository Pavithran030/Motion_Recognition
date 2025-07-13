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

\`\`\`

Motion\_Recognition/

├── dataset/    # Dataset for training/testing

├── models/     # Saved model files

├── scripts/      # Python scripts for detection and recognition

│   ├── capture\_points.py

│   ├── recognize\_action.py

│   └── preprocess\_data.py

├── unity\_integration/    # Unity assets and scripts

│   └── AnimateFromText.cs

├── outputs/       # Result files and logs

├── sample\_videos/       # Example input videos

└── README.md     # Project documentation

\`\`\`

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

python -m venv venv

```
- source venv/bin/activate    # On Windows: venv\Scripts\activate

### 3. Install Dependencies
```bash

pip install -r requirements.txt

```

### 4. Run the Motion Capture Script

```bash
python scripts/capture_points.py

```

### 5. Recognize the Action (Optional)

```bash
python scripts/recognize_action.py
```
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
