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

## **📝 Task Details**  

### 🔹 **Common Test I: Multi-Class Classification**  
- **Goal:** Classify images into three categories: no substructure, subhalo substructure, and vortex substructure.  
- **Model Used:** ResNet-34  
- **Evaluation Metrics:** AUC score, ROC curve
- **Results:**
    - Overall AUC -> 0.9852
    - No Substructure AUC -> 0.991
    - Sphere AUC ->  0.985
    - Vortex AUC -> 0.979
- **Location:** [`Common_Task/`](Common_Task/)
- **Pretrained Weights:** [`Common Task Weights`](https://drive.google.com/file/d/1XZCIzpvVOreV0pvC7ZKw6bYa2V7b8S5M/view?usp=sharing)

### 🔹 **Specific Test IV: Diffusion Task**  
- **Goal:** Develop a generative model to simulate realistic strong gravitational lensing images
- **Evaluation Metrics:** Fréchet Inception Distance (FID)
- **Result:** FID -> 3.5294
- **Location:** [`Diffusion_task_4/`](Diffusion_task_4/)
- **Pretrained Weights:** [`Diffusion_task_weights/`]([Diffusion_task_4](https://drive.google.com/file/d/1RzSDhRZ8YLXZQqF6-QCbGHOheXA0t17-/view?usp=sharing)

## 🚀 **Running the Code**  
To setup the enviornment and run the code, follow the instructions in  [`Common task README.md/`](Common_Task/) for common task and [`DIffusion README.md/`](Diffusion_task_4/) for Diffusion task 
