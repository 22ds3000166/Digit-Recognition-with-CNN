
# 🧠 Handwritten Digit Recognition System

## 📁 Project Structure

```
├── canvas.py          # Tkinter GUI for drawing digits
├── model.ipynb        # Jupyter notebook for training the CNN using PyTorch
├── model.pt           # Trained PyTorch model (generated after running model.ipynb)
├── model_server.py    # FastAPI server for digit prediction
└── README.md          # You're here!
```

---

## ⚙️ Setup Instructions

### 🔧 1. Clone the Repository

```bash
git clone https://github.com/your-username/digit-recognition-project.git
cd digit-recognition-project
```

### 📦 2. Install Dependencies

Ensure you have Python 3.7+ installed. Then install the required packages:

```bash
pip install -r requirements.txt
```

**Dependencies include:**

* `torch`
* `torchvision`
* `fastapi`
* `uvicorn`
* `numpy`
* `matplotlib`
* `pillow`
* `tkinter` (pre-installed with most Python distributions)

> If `tkinter` isn't available, you can install it via your system package manager.

---

### 🧠 3. Train the Model

Open and run the `model.ipynb` Jupyter Notebook to:

* Load MNIST dataset
* Train a CNN
* Save the trained model as `model.pt`

Alternatively, if `model.pt` is already provided, skip this step.

---

### 🚀 4. Run the FastAPI Server

```bash
python model_server.py
```

This will start the server at:

```
http://127.0.0.1:8000/predict
```

---

### 🖼️ 5. Launch the Drawing App

```bash
python canvas.py
```

* Draw any digit (0–9) using the mouse.
* Click **"Predict"** to get the digit prediction.
* Uses the FastAPI backend for real-time inference.

---

## 🔍 How It Works

* The **Tkinter Canvas** lets the user draw a digit.
* The image is resized to `28x28`, converted to grayscale.
* It is sent to the FastAPI server as a PNG image.
* The **CNN model** processes it and predicts the digit.
* The result is shown in a popup using `tkinter.messagebox`.

---

## 📊 Model Architecture

The CNN model used in this project:

```python
Conv2d(1, 32, kernel_size=3) → ReLU → MaxPool
→ Conv2d(32, 64, kernel_size=3) → ReLU → MaxPool
→ Flatten → Linear(64*5*5, 128) → ReLU → Linear(128, 10)
```

Trained on the MNIST dataset with accuracy reaching \~98%.




