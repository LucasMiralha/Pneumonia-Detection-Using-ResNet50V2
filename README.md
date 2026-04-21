# Pneumonia Detection Using ResNet50V2 Transfer Learning

Professional implementation of a Deep Learning model for the classification of pediatric pneumonia using chest X-ray images. This project utilizes the **ResNet50V2** architecture through transfer learning, achieving high-precision results through individual hyperparameter optimization.

---

Done as part of the Computational Intelligence 2 class, taught by professor [Polyana Fonseca Nascimento](https://www.linkedin.com/in/polyana-fonseca-nascimento/)

## 👥 Authors (Team)

*   **Lucas Almeida Miralha de Figueiredo** - [GitHub Profile](https://github.com/LucasMiralha) | [LinkedIn](https://www.linkedin.com/in/lucas-figueiredo-844a2a277/)
*   **Carlos Henrique Miranda Esteves** - [GitHub Profile](https://github.com/10CarlosEsteves) | [LinkedIn](https://www.linkedin.com/in/carlos-henrique-miranda-esteves-b42aaa244/)
*   **Lucas Andrey Nunes de Aragão** - [GitHub Profile](https://github.com/Luckandrey) | [LinkedIn](https://www.linkedin.com/in/lucasandreyaragao/)

## 📖 Project Overview

This project is inspired by the foundational research paper [*"Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning"*](https://doi.org/10.1016/j.cell.2018.02.010) published in *Cell* (2018). The core objective is to develop a robust binary classifier capable of distinguishing between "Normal" and "Pneumonia" cases in pediatric chest X-rays.

### Theory and Dataset
- **Theorical Basis**: Principles from *"Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow"* by Aurélien Géron.
- **Dataset**: [Chest X-Ray Pneumonia (Balanced Dataset)](https://www.kaggle.com/datasets/yusufmurtaza01/chest-xray-pneumonia-balanced-dataset) available on Kaggle.
- **Architecture**: **ResNet50V2** (Residual Network), pre-trained on ImageNet, with custom top layers for classification.

---

## 🚀 Hyperparameter Optimization

There was an initial model optimization using GridSearch, after that, each team member focused on a specific aspect of the model's architecture and training process through systematic GridSearch-like experiments. As per demmanded by the class professor

### 1. Dense Layer Neurons Analysis
**Conducted by: Carlos Esteves**
Explored the impact of the number of neurons in the final dense layer to find the optimal trade-off between information compression and pattern detection.
*   **Range tested**: [64, 128, 256, 512, 1024]
*   **Best Configuration**: **128 Neurons**
*   **Performance**:
    *   **Validation Accuracy**: 0.9779
    *   **Validation Loss**: 0.0669

### 2. Activation Function Comparison
**Conducted by: Lucas Andrey**
Tested various activation functions in the hidden layers to enhance gradient flow and learning efficiency.
*   **Functions tested**: `ReLU`, `LeakyReLU`, `Swish`, `Softplus`
*   **Best Configuration**: **Swish Activation**
*   **Performance**:
    *   **Validation Accuracy**: 0.9763
    *   **Validation Loss**: 0.0657
    *   **Validation Recall**: 0.9650

### 3. Training Epochs & Convergence Analysis
**Conducted by: Lucas Miralha**
Analyzed model convergence over extended training periods, without Early Stopping to analyse real learning or overfitting while maximizing accuracy.
*   **Epochs tested**: [10, 25, 50, 75, 100]
*   **Best Configuration**: **100 Max Epochs**
*   **Performance**:
    *   **Validation Accuracy**: 0.9909
    *   **Validation Loss**: 0.0281
    *   **Validation Recall**: 0.9844

---

## 🛠️ Reproducibility and Usage

To reproduce the results or use the model locally:

### 1. Environment Setup
Clone the repository and install the required dependencies:
```bash
git clone https://github.com/LucasMiralha/Pneumonia-Detection-Using-ResNet50V2
cd Pneumonia-Detection-Using-ResNet50V2
pip install -r requirements.txt
```

### 2. Running the Project
The project is organized into Jupyter Notebooks:
*   `ResNet50V2 Transfer Learning on a Chest X-Ray Pneumonia Classification.ipynb`: The main pipeline and final model.
*   Specific tuning results can be found in the `(Name Hyperparameters) ...` notebooks.

### 3. Dataset Integration
As the project was developed using Google Colab, it is necessary to adjust the paths in the `1°: Data Processing` section of the notebook.
*   If running locally, it's recommended to use the OS python lib to adjust the pathing.
*   If running on Google Colab, it's recommended to use the Google Colab drive lib to mount your drive

---

## 🤖 Generative AI Transparency

In accordance with modern academic and technical standards, we disclose that **Gemini 3.1** was utilized as an assistant during this project. Its role included:
- Refactoring and optimizing Python code structures.
- Assisting in the creation of comprehensive documentation (README and requirements).
- Debugging environmental and library-specific issues.

---

## 📚 References

1.  **Kermany, Daniel S. et al.** (2018). *Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning*. Cell, Volume 172, Issue 5, 1122 - 1131.e9. [Link to Paper](https://doi.org/10.1016/j.cell.2018.02.010)
2.  **Géron, A.** (2019). *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow*. O'Reilly Media.
3.  **Kaggle Dataset**: [Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/datasets/yusufmurtaza01/chest-xray-pneumonia-balanced-dataset).

---
*Developed for academic and research purposes. Accuracy and loss values might vary slightly based on hardware (GPU) and random seeds.*
