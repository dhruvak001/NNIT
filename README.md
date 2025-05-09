# NNIT – Neural Networks for Images & Texts

A unified PyTorch framework for loading data, defining models, running experiments, and training/testing deep networks on both image and text tasks.

---

## 📖 Overview
This repository (“NNIT”) presents a complete deep‑learning pipeline:
- **Data loading & preprocessing** (images & text)  
- **Model definitions** in `model/` (CNNs, RNNs, Transformers, etc.)  
- **Experiment scripts** in `Experiments/` for rapid prototyping  
- **Final training & evaluation** code in `train.py` and `Train_Test.py`  
- **Pretrained checkpoints** and logs in `Final_Model/`

You can plug in your own datasets or architectures and reproduce state‑of‑the‑art results with minimal boilerplate.

---

## 📂 Repository Structure
NNIT/  
├── Experiments/ # interactive notebooks & quick prototyping scripts  
├── Final_Model/ # saved weights, inference demos, logs  
├── model/ # PyTorch model definitions (CNN, RNN, Transformer)  
├── load_data.py # dataset classes & preprocessing utilities  
├── train.py # main training script with config flags  
├── Train_Test.py # end‑to‑end train + evaluate pipeline  
├── requirements.txt # Python dependencies  
├── .gitignore  
└── LICENSE # GPL‑3.0  


## Installation

1. **Clone the repo**  
    git clone https://github.com/dhruvak001/NNIT.git  
    cd NNIT  

2. **Create a virtual environment (recommended)**  
    python3 -m venv venv  
    source venv/bin/activate   # On Windows: venv\Scripts\activate  

3. **Install dependencies**  
    pip install -r requirements.txt  

---

## Quickstart

### 1. Load & Inspect Data  
    python load_data.py \
      --task image_classification \
      --dataset CIFAR10 \
      --batch-size 64

### 2. Run an Experiment  
    python Experiments/my_experiment.py \
      --epochs 20 \
      --lr 1e-3

### 3. Train & Validate  
    python train.py \
      --model resnet18 \
      --data-dir ./data \
      --epochs 50 \
      --save-dir Final_Model/checkpoints

### 4. Full Train/Test Pipeline  
    python Train_Test.py \
      --config configs/cifar_resnet18.yaml

---

## Customization

- **Add new models**: drop a `.py` file in `model/` following the `BaseModel` interface.  
- **New datasets**: extend `load_data.py` with your own `Dataset` subclass.  
- **Hyperparameters**: pass flags to `train.py` or define in `configs/`.

---

## License

This project is licensed under the **GPL‑3.0** License. See [LICENSE](LICENSE) for details.
