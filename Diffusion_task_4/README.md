# GSOC-25 DeepLense Diffusion Task

<p align="center">
  <img src="https://github.com/AarjavSatia/GSOC-24_DeepLense_Diffusion_Task/blob/main/images/diffusion_sample-1.png"?raw=true" alt="Lensing samples generated through diffusion."  width="400" height="400" /> 
</p>
<p align="center">Fig. Lensing samples generated through diffusion <strong>(FID : 3.5294)</strong></p>

## 🚀 Setup

Follow these steps to set up and run the project locally.

### 1️⃣ Clone the Repository  
```sh
git clone https://github.com/AarjavSatia/GSOC25_DeepLense_Task.git
cd GSOC25_DeepLense_Task/Diffusion_task_4
```
### 2️⃣ Create Conda Enviornment  
```sh
conda create -n diffusion_task python==3.12
```
### 3️⃣📦 Install Dependencies
```sh
pip install -r requirements.txt
```

### 4️⃣🚀 Run the Project 
Run the GSOC'25_DeepLense_Diffusion-task.ipynb file


## Dataset:
<p>The dataset consists a total of 10,000 greyscale images stored as numpy arrays. The arrays are first converted to greyscale PIL images and then resized to 128x128 to make it a multiple of 8. (to account for proper U-Net downsampling and Upsampling) They are then converted to tensors normalized to a range [0,1]. </p>  
<p>Few images from the dataset are shown below:</p>

<p align="center">
  <img src="https://github.com/AarjavSatia/GSOC-24_DeepLense_Diffusion_Task/blob/main/images/diffusion_data_description.png"?raw=true" alt="Example samples from the dataset"  /> 
</p>



## Model Features and Results:
<p>1) Denoising Diffusion Probalistic Model (DDPM) is used for all experimentations, the code takes from https://github.com/lucidrains/denoising-diffusion-pytorch and https://github.com/openai/improved-diffusion.</p>
<p>2) For the forward process Sigmoid Beta Scheduling[1] is used to create beta timesteps as it gives better results on images greater than 64x64. </p>
<p>3) DDIM sampling[2] method is used for sampling as it is decreases the time taken for sampling thus allowing for calculation of FID on large number of samples giving a more robust FID score.</p>
<p>4) Exponential Moving Average is used for updating the weights which enables smoother training and makes sampling more stable. </p>
<p>5) U-Net model takes from the original Open-AI architecture, but uses a scaled down version with fewer parameters to keep the model computationally light. Futher, Flash attention[3] is used in the attention layers to increase training speed.</p>
<p>6) FID score is calculated by generating 2,500 samples at 1,000 sampling steps for 2,048 inceptionv3 features. Final FID value comes out to be <strong>3.5294</strong>. (Pre-Samples download link - https://drive.google.com/file/d/1AQKP2Je0vauMAIFiQL-JN9u96w3SNezO/view?usp=sharing )</p>

### Further Modifications and Ideas:
<p>1) Given a large dataset U-Net backbone can be replaced with other architectures like U-ViT, Karras U-Net and Transformers (DiT).</p>
<p>2) Vector-Quantized Variational Auto-Encoder's (VQ-VAE) Encoder and Decoder can be used to compress the images to a Latent space and diffusion process can be applied on that latent space so as to reduce the computational complexity i.e Latent Diffusion Models (LDE).</p>
<p>3) Given more information, U-Net can be conditioned on various properties of strong lensing images (like their substructure and various other parameters describing their structure) to generate accurate and specific lensing images.</p>

## References:
<p>[1] Jabri, A., Fleet, D., & Chen, T. (2022). Scalable adaptive computation for iterative generation. arXiv preprint arXiv:2212.11972.</p>
<p>[2] Song, J., Meng, C., & Ermon, S. (2020). Denoising diffusion implicit models. arXiv preprint arXiv:2010.02502.</p>
<p>[3] Dao, T., Fu, D., Ermon, S., Rudra, A., & Ré, C. (2022). Flashattention: Fast and memory-efficient exact attention with io-awareness. Advances in Neural Information Processing Systems, 35, 16344-16359.</p>

