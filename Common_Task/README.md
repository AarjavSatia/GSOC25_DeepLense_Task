# GSOC-25 DeepLense Common Task - Classification



Classwise ROC             |  Average ROC
:-------------------------:|:-------------------------:
![ROC plot showing individual ROC curves for all three classes](https://github.com/AarjavSatia/GSOC-24_DeepLense_Common_Task/blob/main/images/MultiROC_1.png?raw=true)  | ![ROC plot showing an average ROC curve for all three classes](https://github.com/AarjavSatia/GSOC-24_DeepLense_Common_Task/blob/main/images/MultiROC_2.png?raw=true)
<p align="center">Fig. The left plot shows class wise AUC scores with 0 class corresponding to 'no_substructure' 1_class to 'sphere' and 2 class to 'vort'. The right plot shows the average AUC over all three classes.</strong></p>


## 🚀 Setup

Follow these steps to set up and run the project locally.

### 1️⃣ Clone the Repository  
```sh
git clone https://github.com/AarjavSatia/GSOC25_DeepLense_Task.git
cd GSOC25_DeepLense_Task/Common_Task
```
### 2️⃣ Create Conda Enviornment  
```sh
conda create -n common_task python==3.12
```
### 3️⃣📦 Install Dependencies
```sh
pip install -r requirements.txt
```

### 4️⃣🚀 Run the Project 
Run the GSOC'25_DeepLense_classification_common_task.ipynb file


## Dataset:
### Dataset Description:
<p>The dataset consists of 30,000 training images and 7,500 validation images, all of size 150x150 pixels. All images are stored as one channel numpy arrays. In the training set each class (no, sphere and vort) has an equal distribution  of 10,000 samples each. The same is followed in the validation set.</p> 
<p>The three classes of the data are shown below:</p> 

<p align="center">
  <img src="https://github.com/AarjavSatia/GSOC-24_DeepLense_Common_Task/blob/main/images/classification_data_description.png?raw=true" alt="Three classes of the data."  /> 
</p>

#### Dataset Preprocessing
<p>The numpy arrays are first converted into 3 channel PIL images and then finally resized to 224x224x3 pixels. They are then converted to tensors and normalized in the range [-1,1]. Data augmentations like Horizontal flipping are also applied to make the model more robust.</p>  

## Model Features:

<p>1) The main idea is to build upon previous papers [1], [2] that have performed classification on strong lensing images and that is why Resnet34 model pretrained on ImageNet dataset has been used for classification. The model is simple, lightweight and effective.</p>
<p>3) Among the 7500 validation images 90% are used during training as validation and 10% are used to conduct different tests to evaluate the model.</p>
<p>4) Model performs well and gets an accuracy of <strong>92.67%</strong> on the test data and attains an average AUC score of <strong>0.9852</strong>.
With class individual AUC score being <strong>0.991</strong> for no substructure, <strong>0.985</strong> for sphere and <strong>0.979</strong> for vort. </p>

## Further Modifications and Ideas:
<p>1) Given a larger dataset, transformer based models like ViT and Swin-Transformers can be tried out.</p>
<p>2) Attetnion modules can be encorporated to the base Resnet models giving the model global awareness from attentionvmodule and high inductive bias from the CNN.</p>

## References:
<p>[1] Alexander, S., Gleyzer, S., McDonough, E., Toomey, M. W., & Usai, E. (2020). Deep learning the morphology of dark matter substructure. The Astrophysical Journal, 893(1), 15.</p> 
<p>[2] Alexander, S., Gleyzer, S., Parul, H., Reddy, P., Toomey, M. W., Usai, E., & Von Klar, R. (2020). Decoding dark matter substructure without supervision. arXiv preprint arXiv:2008.12731.</p>
<p>[3] He, K., Zhang, X., Ren, S., & Sun, J. (2016). Deep residual learning for image recognition. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 770-778).</p>




