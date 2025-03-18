## GSOC-24 DeepLense Common Task - Substructure Classification



Individual ROC             |  Average ROC
:-------------------------:|:-------------------------:
![ROC plot showing individual ROC curves for all three classes](https://github.com/AarjavSatia/GSOC-24_DeepLense_Common_Task/blob/main/Images_ROC/MultiROC_1.png?raw=true)  | ![ROC plot showing an average ROC curve for all three classes](https://github.com/AarjavSatia/GSOC-24_DeepLense_Common_Task/blob/main/Images_ROC/MultiROC_2.png?raw=true)

### Model Features:

<p>1) The main idea is to build upon previous papers [1], [2] that have performed classification on strong lensing images that is why Resnet34 model pretrained on ImageNet dataset has been used for classification as it simple, lightweight and effective.</p>
<p>3) Among the 7500 validation images 90% are used during training as validation and 10% are used to conduct different tests to evaluate the model.</p>
<p>4) Model performs well and gets an accuracy of <strong>92.67%</strong> on the test data and attains an average AUC score of <strong>0.9852</strong>.
With class individual AUC score being <strong>0.991</strong> for no substructure, <strong>0.985</strong> for sphere and <strong>0.979</strong> for vort. </p>



### Further Modifications and Ideas:
<p>1) Given a larger dataset, transformer based models like ViT and Swin-Transformers can be tried out.</p>
<p>2) Attetnion modules can be encorporated to the base Resnet models which would give the model global awareness from    attention module and high inductive bias from CNN.</p>

### References:
<p>[1] Alexander, S., Gleyzer, S., McDonough, E., Toomey, M. W., & Usai, E. (2020). Deep learning the morphology of dark matter substructure. The Astrophysical Journal, 893(1), 15.</p> 
<p>[2] Alexander, S., Gleyzer, S., Parul, H., Reddy, P., Toomey, M. W., Usai, E., & Von Klar, R. (2020). Decoding dark matter substructure without supervision. arXiv preprint arXiv:2008.12731.</p>
<p>[3] He, K., Zhang, X., Ren, S., & Sun, J. (2016). Deep residual learning for image recognition. In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 770-778).</p>




