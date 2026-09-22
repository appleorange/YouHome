# 🏠 YouHome: Smart Home Activity Recognition

**YouHome** is a research project from **UIUC** that develops a **privacy-conscious smart home framework** using machine learning to recognize user activities and personalize home environments. The goal is to improve residents’ quality of life and optimize energy efficiency.  

The project uses the **YouHome Activities-of-Daily-Living (ADL) dataset**, containing **~300K RGB images** annotated with daily activities and multiple sensing data (e.g., illuminance, temperature, motion, keypoints).  

---

## Features

- **Activity classification**: Classifies user activities from images.  
- **Privacy-preserving ML**: Focused on safe use of sensitive data.  
- **Model experimentation**: Supports ResNet, EfficientNet, and ConvNeXt architectures.  
- **Data analysis & visualization**: Tracks accuracy, loss, and misclassified examples.  
- **Data augmentation & balancing**: Rotation, flips, grayscale, and weighted sampling.  

---

## Results

| Dataset Size | Model          | Training Accuracy | Test Accuracy |
|-------------|----------------|-----------------|---------------|
| 100K        | ResNet18       | 94.77%          | 90.74%        |
| 130K        | ResNet18       | 95.53%          | 88.34–92.33%  |
| 130K        | EfficientNet   | 92–93%          | ~90–91%       |

**Observations:**  

- Some labels are difficult to classify due to similar activities (e.g., “Enter” vs. “Leave”).  
- Label misclassification and uneven data distribution were key challenges.  
- Weighted loss functions and data augmentation helped improve accuracy for certain labels.  

---

## Project structure

```
YouHome/
├── src/
│   ├── data/        # dataset loading and image transforms
│   ├── models/       # training entry point and evaluation
│   └── utils/         # shared helpers, config parsing, sobel filtering
├── tests/          # unit/experiment scripts
├── tools/          # data exploration and debugging scripts
└── README.md
```

## Installation

```bash
git clone https://github.com/appleorange/YouHome.git
cd YouHome
pip install -r requirements.txt
```

## Usage

Run everything from the repository root so the `src` package resolves correctly:

```bash
python -m src.models.main [args]   # train/evaluate a model
python tests/test_main.py          # run a test script directly
python tools/load_debug_info.py    # run a tools script directly
```
