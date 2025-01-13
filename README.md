# Unsupervised Graph Neural Networks for Brain Network Feature Extraction and Prognosis Prediction in Glioblastoma Using Perfusion MRI

## Project Overview
This project aims to develop a novel **unsupervised Graph Neural Network (GNN)** model for feature extraction from brain network data derived from **perfusion MRI** (pMRI) scans of glioblastoma patients. The extracted features are then utilized for **prognosis prediction** using survival analysis techniques.

## Objectives
- Develop an unsupervised **GNN autoencoder** to extract meaningful features from pMRI data.
- Use the extracted features for **prognosis prediction** through survival analysis.
- Improve the accuracy and reliability of glioblastoma outcome prediction using non-invasive imaging data.

## Methodology
### Data Collection and Preprocessing
- Utilized a dataset of **397 glioblastoma patients** with **Dynamic Susceptibility Contrast (DSC) MRI** scans.
- Preprocessing steps included co-registration, skull stripping, and normalization using **FSL** and **ANTs** tools.

### Model Architecture
- **Autoencoder GNN:** An encoder-decoder model designed to extract latent features from brain network graphs.
- Encoder and Decoder: Each consists of **two graph convolution layers** with ReLU activation and dropout.
- Graph pooling using **global_mean_pool** from PyTorch Geometric.

### Training and Optimization
- **Hyperparameter Optimization:** Conducted using **Optuna** with 200 trials and metrics tracked using validation loss.
- **Optimization Techniques:** Adam optimizer, batch size tuning, dropout regularization, and early stopping.

### Feature Extraction and Survival Analysis
- Extracted features were analyzed using the **Cox Proportional Hazards** (Cox PH) model for survival analysis.
- Identified features **X25 and X82** correlated with patient survival.

## Key Results
- **Significant Predictors:** Clinical features such as **age** and **IDH1 mutation status** were significant predictors of survival.
- **Extracted Features:** Features X25 and X82 showed predictive potential with hazard ratios >2, though requiring further validation.

## Limitations
- **Small Dataset:** Limited data size may affect statistical power.
- **Feature Extraction:** GNN feature extraction might require further refinement.
- **Threshold Adjustment:** Relaxed p-value threshold could lead to false positives.

## Future Work
- Increase dataset size for improved statistical significance.
- Enhance feature extraction techniques, possibly with **variational autoencoders** or multi-scale graph learning.
- Validate model performance on external datasets.

## Repository Structure
- `Data_Cleaning.ipynb`: Data preprocessing and cleaning steps.
- `MSc_Final_Project_Unsupervised_Model.ipynb`: Core notebook for the unsupervised GNN model implementation.
- `Survival_Analysis.ipynb`: Notebook for survival analysis using the extracted features.
- `README.md`: Documentation for the project.

## Technologies Used
- **Python, PyTorch, PyTorch Geometric, NumPy, Pandas, Scikit-learn, Matplotlib, Optuna.**

## Author
**Daniel Abel Fernandes**  
MSc Biomedical Engineering, Imperial College London
