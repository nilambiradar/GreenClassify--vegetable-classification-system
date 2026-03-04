# GreenClassify - A Deep Learning Based Approach For Vegetable Classification
## 📌 Project Overview
This project is a **deep learning-based image classification system** that **identifies different types of vegetables from images.** <br>
The model is trained using Transfer Learning (MobileNetV2) and achieves approximately 99% test accuracy on a dataset containing 15 vegetable classes. <br>
The trained model is saved in .h5 format and deployed using a Flask web application for real-time image prediction.

### 🧠 Model Architecture
- Base Model: MobileNetV2 (Pretrained on ImageNet)
- Transfer Learning Approach
- Custom Classification Head:
- GlobalAveragePooling2D
- Dropout (0.3)
- Dense (128 units, ReLU)
- Output Layer (15 classes, Softmax)

### 📂 Dataset Structure:
<details>
<summary> The dataset is organized as follows: </summary>
vegetable_dataset/ <br>
│ <br>
├── train/ <br>
│   ├── Bean/ <br>
│   ├── Bitter_Gourd/ <br>
│   ├── Bottle_Gourd/ <br>
│   ├── Brinjal/ <br>
│   ├── Broccoli/ <br>
│   ├── Cabbage/ <br>
│   ├── Capsicum/ <br>
│   ├── Carrot/ <br>
│   ├── Cauliflower/ <br>
│   ├── Cucumber/ <br>
│   ├── Papaya/ <br>
│   ├── Potato/ <br>
│   ├── Pumpkin/ <br>
│   ├── Radish/ <br>
│   └── Tomato/ <br>
│ <br>
├── validation/ <br>
│   └── (same structure as train) <br>
│ <br>
└── test/<br>
    └── (same structure as train) <br>
</details>
Total Classes: 15 <br>
Images per class: ~1000 <br>
Total images: ~45,000 <br>

### 🌐 Backend Flow
The model is integrated into a web application where users can:
- Upload an image
- Get predicted vegetable name <br>
**Prediction Process:**
  - Load image
  - Resize to 224×224
  - Normalize (1/255)
  - Predict using model

### 🚀 Training Details <br>
- Image Size: 224 × 224 <br>
- Batch Size: 32 <br>
- Optimizer: Adam <br>
- Loss Function: Categorical Cross entropy <br>
- Data Augmentation: 
  - Rotation <br>
  - Zoom <br>
  - Horizontal Flip <br>
- Early Stopping and Model Checkpoint used <br>
Final Test Accuracy: *~99.6%*

### 🖥️ Frontend Flow <br>
1️⃣ index.html
Landing page with:
  - Project title
  - “Predict the Vegetable” button 
When clicked → redirects to `prediction.html` <br>
2️⃣ prediction.html <br>
- Image upload input
- Submit button
- Sends image to Flask backend
- Backend runs model prediction <br>
3️⃣ logout.html (Result Page)
Displays:
- Predicted vegetable name
- Confidence percentage
Two buttons:
  - Predict Another
  - Back Home

### 🛠️ Installation <br>
1️⃣ Clone the Repository
```bash
git clone https://github.com/wahid-jamadar/vegetable-classification.git
cd vegetable-classification
```
2️⃣ Install Dependencies
```bash
pip install tensorflow flask numpy pillow
```
3️⃣ Run Training (Optional)
```bash
python train-model.py
```
4️⃣ Run Flask App
```bash
python app.py
```
Then open:
```bash
http://127.0.0.1:5000/
```
### 🎓 Learning Outcomes
- Understood the fundamental concepts and techniques of **Convolutional Neural Networks (CNNs).**
- Gained strong understanding of image data and how deep learning models interpret visual features.
- Implement **Transfer Learning** using `MobileNetV2` for efficient model training.
- Trained a deep learning model `best_vegetable_model.h5` using an image dataset of 15,000 images.
- Build and deploy a real-time image classification web application using the `Flask framework.`
- Integrate a trained deep learning model `(.h5)` with a frontend interface.
- Build and deploy a real-time image classification web application using the Flask framework.

### 📌 Author
#### Nilam M. Biradar<br>
B.Tech CSE Student <br>
Dr. D. Y. Patil Agri. & Technical University, Talsande, Kolhapur
