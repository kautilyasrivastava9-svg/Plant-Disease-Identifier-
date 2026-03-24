# Plant-Disease-Identifier-


🌿 Plant Disease Identifier (PyTorch CNN)

A deep learning based image classification model trained on the PlantVillage Dataset to detect plant diseases from leaf images.

This model is built using PyTorch CNN and trained on a subset of the dataset to classify only selected disease categories.

📌 Supported Classes

The model can currently predict the following 15 classes:

Pepper__bell___Bacterial_spot
Pepper__bell___healthy
Potato___Early_blight
Potato___Late_blight
Potato___healthy
Tomato_Bacterial_spot
Tomato_Early_blight
Tomato_Late_blight
Tomato_Leaf_Mold
Tomato_Septoria_leaf_spot
Tomato_Spider_mites_Two_spotted_spider_mite
Tomato__Target_Spot
Tomato__Tomato_YellowLeaf__Curl_Virus
Tomato__Tomato_mosaic_virus
Tomato_healthy


⚠️: THE MODEL CURRENLTY TRAINS ON 4890 IMAGES OF ALL FOLDERS COMBINED , YOU CAN CHANGE IT TO AS PER YOUR SETUP AND NEEDS....


📂 Dataset

Dataset used:
PlantVillage Dataset
Source: Kaggle

Downloaded using:

import kagglehub

path = kagglehub.dataset_download("emmarex/plantdisease")

Subset size used:

4890 images

Train / Test split:

80% Train
20% Test
⚙️ Model Architecture

Custom CNN model:

Input → Conv → BN → ReLU → Pool
      → Conv → BN → ReLU → Pool
      → Conv → BN → ReLU → Pool
      → AdaptiveAvgPool
      → FC → ReLU → Dropout
      → FC → Output

Key Features:

3 Convolution Blocks
Batch Normalization
Dropout Regularization
AdaptiveAvgPool
Fully Connected Classifier
🧠 Training Details
Parameter	Value
Epochs	20
Optimizer	Adam
Learning Rate	0.001
Scheduler	StepLR
Batch Size	64
Image Size	128 × 128
Loss	CrossEntropyLoss
Device	CUDA / CPU

Scheduler:

step_size = 5
gamma = 0.5
📊 Accuracy

After training:

Accuracy ≈ (depends on run)

Printed in output as:

Accuracy : XX.XX
💾 Model Saving
torch.save(model.state_dict(),"plant_disease_identifier.pth")

Saved file:

plant_disease_identifier.pth
🖼️ Prediction on Custom Image

Upload image:

from google.colab import files
uploaded = files.upload()

Prediction output:

I Looked Carefully In The Image ,
And It Seems like Your Crop is suffering from Tomato_Leaf_Mold

Accuracy : XX.XX 

▶️ How to Run
Install dependencies
pip install torch torchvision kagglehub matplotlib pillow
Run training script
Upload leaf image
Get prediction
🚀 Future Improvements
Train on full PlantVillage dataset
Add more crop types
Use ResNet / EfficientNet
Deploy as web app
Convert to mobile model
📜 License

Dataset belongs to original authors of
PlantVillage Dataset

Code is free to use for research / learning.

👨‍💻 Author
Kautilya Srivastava

Deep Learning Project
PyTorch CNN
Plant Disease Detection
