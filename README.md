# Bear Species Image Classifier

This project is a deep learning image classifier that can recognize five different types of bears:

- **Black Bear**
- **Brown Bear**
- **Polar Bear**
- **Panda Bear**
- **Teddy Bear** (added as a fun extra class)

The model is trained using TensorFlow, Keras, and MobileNetV2 with Transfer Learning.
Images were stored in Google Drive and the project was developed and trained in Google Colab.

---

## Project Structure

```
bear-classifier-ai/
│
├── BearClassifier.ipynb       # Main training notebook
├── bear_classifier.h5         # Saved trained model
├── README.md                  # Project documentation
```

---

## Features

- Classifies 5 bear categories with high accuracy
- Uses MobileNetV2 pretrained on ImageNet
- Fast training with free GPU in Google Colab
- Clean and simple model architecture
- Beginner-friendly dataset loading using `flow_from_directory`
- Easy to deploy using Gradio or HuggingFace Spaces

---

## How It Works

Dataset is organized in Google Drive into separate folders:

```
black_bear/
brown_bear/
polar_bear/
panda_bear/
teddy_bear/
```

Colab loads the dataset using:
```python
datagen.flow_from_directory(...)
```

**Model architecture:**

- MobileNetV2 (base, frozen)
- GlobalAveragePooling2D
- Dense(128, relu)
- Dense(5, softmax)

Model is trained for ~10 epochs.

The trained model is saved as `bear_classifier.h5`.

---

## Technologies Used

- Python
- TensorFlow / Keras
- MobileNetV2 (Transfer Learning)
- Google Colab
- Google Drive for dataset storage

---

## Saved Model

The file `bear_classifier.h5` contains the full trained TensorFlow model.

You can load it using:

```python
from tensorflow.keras.models import load_model
model = load_model("bear_classifier.h5")
```
