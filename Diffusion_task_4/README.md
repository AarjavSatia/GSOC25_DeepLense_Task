# GSOC-24 DeepLense Diffusion Task

<p align="center">
  <img src="https://github.com/AarjavSatia/GSOC-24_DeepLense_Diffusion_Task/blob/main/diffusion_samples/diffusion_sample-1.png"?raw=true" alt="Sublime's custom image"  width="400" height="400"/>
</p>

### Model Features and Results:
<p>1) Denoising Diffusion Probalistic Model (DDPM) is used for all experimentations, the code takes from https://github.com/lucidrains/denoising-diffusion-pytorch and https://github.com/openai/improved-diffusion.</p>
<p>2) For the forward process Sigmoid Beta Scheduling[1] is used to create beta timesteps as it gives better results on images greater than 64x64 </p>
<p>3) DDIM sampling[2] method is used for sampling as it is decreases the time taken for sampling thus allowing for calculation of FID on large number of samples giving a more robust FID score.</p>
<p>4) Exponential Moving Average is used for updating the weights which enables smoother training make the model more stable. </p>
<p>5) U-Net model takes from the original Open-AI architecture, but uses a scaled down version with fewer parameters to keep the model computationally light. Futher, Flash attention[3] is used in the attention layers to increase training speed.</p>
<p>6) FID score is calculated by generating 2,000 samples at 250 sampling steps. Final FID value comes out to be <strong>12.3997</strong>.</p>

### Further Modifications and Ideas:
<p>1) Given a large dataset U-Net backbone can be replaced with a Transformer backbone to create a Diffusion Transformer architecture /cite{}.</p>
<p>2) Vector-Quantized Variational Auto-Encoder's (VQ-VAE) /cite{} Encoder and Decoder can be used to compress the images to a Latent space and diffusion process can be applied on that latent space so as to reduce the computational complexity.</p>
<p>3) Given more information, U-Net can be conditioned on various properties of strong lensing images (like their substructure and various other parameters about their vortex, subhalo etc.) to generate accurate and specific lensing images.</p>

### References:
<p>[1] Jabri, A., Fleet, D., & Chen, T. (2022). Scalable adaptive computation for iterative generation. arXiv preprint arXiv:2212.11972.</p>
<p>[2] Song, J., Meng, C., & Ermon, S. (2020). Denoising diffusion implicit models. arXiv preprint arXiv:2010.02502.</p>
<p>[3] Dao, T., Fu, D., Ermon, S., Rudra, A., & Ré, C. (2022). Flashattention: Fast and memory-efficient exact attention with io-awareness. Advances in Neural Information Processing Systems, 35, 16344-16359.</p>

