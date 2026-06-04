# Ocean Oil Spill Detection: Custom Hybrid Architecture 

## Overview
This repository contains the experimentation and training pipeline for a **Custom Hybrid Deep Learning Model** designed for the semantic segmentation of oil spills in satellite imagery. 

Developed as part of a 1st Place winning ML Hackathon project, this specific codebase isolates the hybrid architecture—combining the strengths of DeepLabV3+ and U-Net with a ResNet50 backbone. The goal of this architecture is to accurately identify and segment marine pollution to support rapid environmental response systems.

*Note: This repository focuses purely on the model architecture and benchmarking pipeline. The full full-stack application and Gradio interface can be found in the main project repository.*

## Features
* **Custom Hybrid Architecture:** Integrates DeepLabV3+ spatial pooling with a U-Net inspired decoder.
* **Feature Extraction:** Utilizes an ImageNet pre-trained ResNet50 backbone.
* **Context Module:** Implements Atrous Spatial Pyramid Pooling (ASPP) to capture multi-scale contextual information.
* **Data Processing:** Handles complex satellite imagery with severe class imbalances.
* **Benchmarking:** Evaluates the hybrid approach against standard U-Net and DeepLabV3 models.

## Technologies Used
* **Languages:** Python
* **Deep Learning Frameworks:** TensorFlow, Keras
* **Computer Vision:** OpenCV, PIL
* **Data Science:** NumPy, Pandas, Matplotlib, Seaborn
* **Environment:** Kaggle Notebooks

## Dataset & Classes
The model was trained and evaluated on high-resolution satellite imagery (incorporating AIS vessel tracking data) annotated with corresponding segmentation masks.

| Class | Description |
| :--- | :--- |
| 0 | Background |
| 1 | Oil Spill |
| 2 | Ship |
| 3 | Land |
| 4 | Vegetation |

## Model Architecture Highlights
* **Encoder:** ResNet50 (Pre-trained) for robust feature extraction.
* **Context Block:** ASPP layers to process varying resolutions without losing spatial dimensions.
* **Decoder:** Skip connections bridging the encoder features directly to the upsampling layers, recovering fine-grained spatial boundaries of the oil spills.
* **Output:** Pixel-wise multi-class segmentation utilizing a Softmax activation function.

## Key Benchmarks & Results
This hybrid architecture was developed to test hypothesis-driven improvements in spill localization. Through rigorous evaluation against standard architectures, the project achieved peak performance metrics in the final deployment using optimized segmentation techniques:
* **Precision:** 95.89%
* **Recall:** 96.19%
* **F1-Score:** 95.80%

## Repository Structure
```text
oil-spill-hybrid-segmentation/
│
├── .gitignore
├── LICENSE
├── README.md
└── oil-spill-hybrid.ipynb
Author
Naina Agarwal
BTech Computer Science (Data Science)
Bangalore Institute of Technology

Passionate about leveraging Machine Learning, Computer Vision, and advanced data structures to build real-world solutions for environmental monitoring and automated systems.

License
This project is licensed under the MIT License - see the LICENSE file for details.
