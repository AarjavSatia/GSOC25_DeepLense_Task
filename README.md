# **DeepLense GSoC'25 Evalution Task**  

This repository contains my submissions for the **DeepLense GSoC 2025 evaluation tests**, including:  
- **Common Test I: Multi-Class Classification Task**  
- **Specific Test IV: Diffusion Task**  

## 📂 **Repository Structure**  
```
GSOC25_DeepLense_Task/
│── Common_Task/   # Multi-class classification task
    │──images/
    │──GSOC'25_DeepLense_classification_common_task.ipynb/
    │──GSOC'25_DeepLense_classification_common_task.pdf/
    │──requirements.txt
    │──README.md
│── Diffusion_task_4/   # Diffusion specific task
    │──images/
    │──GSOC'25_DeepLense_Diffusion-task.ipynb/
    │──GSOC'25_DeepLense_Diffusion-task.pdf/
    │──requirements.txt
    │──README.md
```

## **📝 Test Details**  

### 🔹 **Common Test I: Multi-Class Classification**  
- **Goal:** Classify images into three categories: no substructure, subhalo substructure, and vortex substructure.  
- **Model Used:** Vision Transformer (ViT)  
- **Evaluation Metrics:** AUC score, ROC curve  
- **Location:** [`common_test_01/`](common_test_01/)  

### 🔹 **Specific Test IV: Diffusion Task**  
- **Goal:** Train a **Masked Autoencoder (MAE)** on no_sub samples and fine-tune it for multi-class classification and super-resolution.  
- **Steps:**  
  1. Pre-train an MAE on no_sub samples for feature learning.  
  2. Fine-tune it for classification on the full dataset.  
  3. Further fine-tune it for a **super-resolution** task.  
- **Evaluation Metrics:** AUC score (classification), MSE/SSIM/PSNR (super-resolution).  
- **Location:** [`specific_test_06/`](specific_test_06/)  

## 🚀 **Running the Code**  
To setup the enviornment and run the code, follow the instructions in  [`Common task README.md/`](Common_Task/) for common task and [`DIffusion README.md/`](Diffusion_task_4/) for Diffusion task 
