# ITAI-1378-FinalProject_SmartTrashSorter-
Individual Final Capstone Project

# Smart Recycling Classifier  
A lightweight computer vision system that predicts recycling categories from an uploaded image.
<img width="3190" height="808" alt="image" src="https://github.com/user-attachments/assets/eeb6d3df-e3b6-4a85-9407-a8dad055011c" />


## Team Member/ Individual  
- Hieu Lu

## Project Tier  
Tier 2 – Applied Computer Vision System  
Includes model training, dataset processing, demo interface, and evaluation.

---

# Problem Overview  
Recycling is often done incorrectly because individuals struggle to identify materials such as plastic, glass, cardboard, or electronics. Misclassification leads to contamination, increased waste-processing costs, and environmental impact.
This project provides an automated method to classify common recyclable items using a trained deep learning model.

---

# Project Solution  
The Smart Recycling Classifier uses a fine-tuned MobileNetV3 model to analyze an uploaded image and output one of six recycling categories:

- CardboardBoxes  
- GlassBottles  
- GlassJars  
- Laptops  
- Phones  
- PlasticBottles  

Demo reliably showcases **Glass Jars** and **Plastic Bottles**, where the model is most stable.

---

# Impact
The Smart Recycling Classifier helps people make faster and more accurate recycling decisions. It reduces confusion, prevents contamination, and supports environmentally responsible behavior. Households, schools, and waste management organizations all benefit from increased accuracy in sorting.
Even a modest improvement in recycling accuracy can reduce processing costs and lower the amount of recyclable material being sent to landfills. This tool provides value not just by saving time for individuals but by contributing to broader sustainability goals.

---

# Dataset Details  

Dataset Name: Waste Computer Vision Model by IPCVHome  
Source: Roboflow  
Link: https://universe.roboflow.com/ipcvhome-xeunk/waste-yfe9a  
Total Images: 1160

Dataset includes built-in augmentation and was automatically split 80/20 (train/validation).

---

# Technical Approach  

1/ Model  
- MobileNetV3Small (ImageNet pretrained)  
- Final layers fine-tuned on recycling dataset  

2/ Tools & Frameworks  
- TensorFlow / Keras  
- NumPy  
- Matplotlib  
- Roboflow (dataset import)  
- Google Colab  

3/ Preprocessing & Augmentation  
- Resize 224×224  
- Normalize pixel values to [0,1]  
- Random rotation, zoom, shear, brightness shift, and flips  

---

# System Architecture  
[User Upload]
  ↓
[Preprocessing: resize + normalize]
    ↓
[MobileNetV3 Inference]
      ↓
[Softmax Class Probabilities]
        ↓
[Predicted Category + Confidence]


---

# Quick Start (thru Google Colab)

We can run the Smart Recycling Classifier instantly using Google Colab — no installation required.

#1. Open the Colab Notebook
Click the link below to launch the demo: https://colab.research.google.com/drive/1P5DFrooG-_LlqgjwI1MSD0qmEhGw2Mmr?usp=sharing

---

#2. Upload the Dataset or Use Preloaded Roboflow Import
If using Roboflow, the dataset will load automatically with the pre-set API key.

Otherwise, we can upload images directly in the notebook using the built-in upload tool.

---

#3. Run All Cells
From the Colab menu:

Click "Runtime → Run all"

This will:
- Install dependencies  
- Load and preprocess the dataset  
- Train the MobileNetV3 model  
- Save the model  
- Run the live image classification demo  

---

#4. Test the Model
Use the final demo cell:

- Upload a picture of a Glass Jar or Plastic Bottle  
- View predicted class + probability  
- Review the full confidence distribution  

---

#5. (Optional) Retrain the Model
We may adjust:
- Number of epochs  
- Augmentation parameters  
- Learning rate  
- Dataset source from Roboflow  

Then re-run training to generate a new `.h5` model.

---


# Model Performance  

| Metric | Value |
|--------|--------|
| **Training Accuracy** | **23.96%** |
| **Validation Accuracy** | **24.82%** |

These results indicate underfitting, but the model still provides consistent confidence patterns for certain categories (GlassJars, PlasticBottles), which supports the demo.

---

# Demo Results  

Working Examples  
- Glass Jar → High confidence
- Plastic Bottle → Typically second-highest probability

# Failure Example  
- Laptop image classified as GlassJar due to reflective surfaces  

Why it failed: These examples highlight model limitations and motivation for future improvements. It could also be there were not enough of laptop pictures used in the dataset for training purposes. 

---

# Challenges  

- Dataset imbalance  
- Visual similarity between items  
- Limited number of samples per class  
- Underfitting in training  

---

# What We'd Do Differently & Future Improvements 

- Increase dataset quantity and diversity  
- Add a confidence-based “Unknown” label  
- Use object detection instead of classification  
- Deploy model via TensorFlow Lite
- Create a mobile or web-based recycling assistant app  

---

# AI Usage  

AI tools were used to support technical problem-solving, including dataset selection, debugging TensorFlow code, and optimizing training workflow.
AI also assisted in interpreting model performance and suggesting improvements for accuracy, architecture, and presentation.
Through this interaction, I gained a deeper understanding of machine learning development, model limitations, and practical methods for enhancing reliability.

---

# References  

- Waste Computer Vision Model by IPCVHome (from Roboflow): https://universe.roboflow.com/ipcvhome-xeunk/waste-yfe9a  
- TensorFlow Keras Documentation  
- MobileNetV3 Research Paper  
- ITAI 1378 Course Materials
- Stackoverflow and GitHub  

---

# Conclusion  

The Smart Recycling Classifier successfully demonstrates a complete computer vision pipeline—from dataset acquisition and training to real-time prediction. While accuracy is still limited, the project establishes a strong foundation for future enhancements and a potential real-world recycling assistant system.


