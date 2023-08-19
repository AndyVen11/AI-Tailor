# AI Tailor


TAILOR AI Art Generator is a mobile application designed to provide users with 
the ability to generate unique and creative fashion designs using artificial 
intelligence. This implementation is built on top of the excellent Stable Diffusion Model.

![stablediffusion_overview](https://github.com/amgad59/Your-AI-Tailor/assets/76216074/b2d1c781-7bd0-46ff-8211-9bac3d3f88ab)

Image Source : [Understanding Stable Diffusion from "Scratch"](https://scholar.harvard.edu/binxuw/classes/machine-learning-scratch/materials/stable-diffusion-scratch)

## Preview
[Watch Video](https://youtu.be/o25sxSxPwto)
## Datasets
1) First Dataset:   
   * fashion product dataset, Kaggle. 21K of fashion products images 
divided into two subcategories (top wear, bottom wear)  
   * 10 features describing the product such as gender, base color, year,
2) Second Dataset:  
   * 500 collected wedding dresses images with detailed description.  
   * Preprocessing done on images: face segmentation, background.   
   * Preprocessing done on text: summarize the text prompt by getting the 
most important sentences in the description, enter the output of step 1 
to T5-transformer to summarize the description according to the 
meaning of the entered sentences.
## Preprocessing Techniques:
1) Image preprocessing:  
• Remove background:   
Remove the background from the images and saves the output to 
improve the quality and accuracy of image generation.  
• Face Segmentation:  
Using face segmentation techniques, We remove the faces of the models posing for the pictures as it greatly increase the model accuracy and produce better results
2) Text preprocessing:  
• Summarize using the spaCy:  
Summarize the text prompt by getting the most important sentences 
in the description using the spaCy natural language processing 
library.
• Summarization using T5-transformer:
The function takes a data generated from summarization using the 
spaCy containing the summarized text descriptions and generates a 
new summary for each description using the T5-transformer model as it helps us keeping the description under 65 words.
- <b>Training</b>
  * Basic usage `python ModelTraining.py`
  * Options
      - `diffusion model`
      - `VAE`
      - `noise scheduler`
      - `flag for mixed precision training`
## Setup Configuration:
Code was trained and tested using Google Colab with python 3.9, 
Tensorflow, Keras, Torchvision, It was run on GPU: NVIDIA V100, 
System RAM: 83.5GB, GPU RAM: 40 GB, Disk Storage: 166.8 GB

## Sample Images Generated
Following are the images generated by the generative model from the captions.


| Caption        | Generated Images  |
| ------------- | ----- |
| Thin spaghetti straps grace the shoulder to meet a modern straight neckline with a subtle wrapped effect wedding |  ![Picture1](https://github.com/amgad59/Your-AI-Tailor/assets/76216074/e11bff94-c02f-45e6-b3a2-10d66f37f290) |
| Star Wars        |  ![Picture3](https://github.com/amgad59/Your-AI-Tailor/assets/76216074/edfc39a6-c517-48f0-8fab-3cb621fc5cdd) |


## Implementation Details
- The model was trained for around +90 epochs on a GPU. This took roughly 2-3 days.
- The images generated are 300 x 300 in dimension.
- The train-val split is 0.9.

## Pre-trained Models
- [Stable Diffusion Model](https://github.com/CompVis/stable-diffusion)

## TODO
- Train both models on more images.
- Add more categories.
- enhance the user experience.

## References
[1] Blattmann, A., Rombach, R., Oktay, K. and Ommer, B., 2022. Retrieval-Augmented Diffusion Models. arXiv preprint arXiv:2204.11824.  
[2] Feng, Z., Zhang, Z., Yu, X., Fang, Y., Li, L., Chen, X., Lu, Y., Liu, J., Yin, W., Feng, S. and Sun, Y., 2022. ERNIE-ViLG 2.0: Improving Text-to-Image Diffusion Model with Knowledge-Enhanced Mixture-of-Denoising-Experts. arXiv preprint arXiv:2210.15257.  
[3] Li, R., Li, W., Yang, Y., Wei, H., Jiang, J. and Bai, Q., 2022. Swinv2-Imagen: Hierarchical Vision Transformer Diffusion Models for Text-to-Image Generation. arXiv preprint arXiv:2210.09549.  
[4] Balaji, Y., Nah, S., Huang, X., Vahdat, A., Song, J., Kreis, K., Aittala, M., Aila, T., Laine, S., Catanzaro, B. and Karras, T., 2022. ediffi: Text-to-image diffusion models with an ensemble of expert denoisers. arXiv preprint arXiv:2211.01324.  
[5] Yu, J., Xu, Y., Koh, J.Y., Luong, T., Baid, G., Wang, Z., Vasudevan, V., Ku, A., Yang, Y., Ayan, B.K. and Hutchinson, B., 2022. Scaling autoregressive models for content-rich text-to-image generation. arXiv preprint arXiv:2206.10789.  
[6] Ramesh, A., Dhariwal, P., Nichol, A., Chu, C. and Chen, M., 2022. Hierarchical text-conditional image generation with clip latents. arXiv preprint arXiv:2204.06125.

