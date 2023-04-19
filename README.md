# DirverseGenerator
This is the project I finished at the individual enterprise.  
Because the property of this project belongs to the company, therefore, I can only put some images and do some brief introduction.  
The source code of this project is saving is the GitLab of the individual enterprise I worked in  
I have submitted a patent related to this project.  

Technical Skills and tools:  
1. WGAN-GP  
2. GAN  
3. DCGAN  
4. StyleGAN2  
5. StarGAN  
6. PyTorch  
7. Linux  
8. CUDA  
9. virtualenv  
10. CNN
11. PHash
...  
  
## Problem   
1. In all kinds of GAN methods, dedicated to generate images look like the image in the training dataset. However, these methods cannot generate images with some variety  
2. When the image is too less, GAN are difficult to generate images well  
3. When images have too many categories, the GAN methods will generate confusing images  
I give a example for the second and third points above  
We use the animal drawing images as the training dataset(300 pics), there are more than 30 categories  
Training dataset sample  
![sample](https://user-images.githubusercontent.com/50438750/132112835-78de5b36-ea06-4092-a854-ef942d3945a4.PNG)

The StyleGAN2 generates messy images(The left side), the StarGAN2 generates overlapped images(The right Side)  
![image](https://github.com/ericleee0119/DirverseGenerator/blob/main/image/styleGAN2.PNG) ![image](https://github.com/ericleee0119/DirverseGenerator/blob/main/image/stargan2.PNG)    

## Solution  
We hope we can generate the image with some variety, and is not exist in the real-world, but can understand that is come from our training dataset, for example, a turtle's head combine with bee's body  

I used WGAN-GP as our based model. WGAN-GP will generate the image that is almost same as the training dataset. Then I find the hidden feature in the latent space.  

We use the blur detection and contrast detection to remove the image that is not clear enough until we get 2 clear image.  

We get images from the latent space between these 2 images, and do the blur detection and contrast detection again to remove blur images.  

We do the similarity detection between the image we just generated and the image in the training dataset to remove the image that is too similar to the training dataset  

We tell the discriminator the image we expect, then the discriminator will tell the generator which kind of images it should generate  

After the traning, we can get the WGAN-GP model that will generate images that are full of variety  

The below image shows the result. The left part is the training dataset, the middle part is the original result from the WGAN-GP that is too similar to the training dataset, the right part is our method's variety result  

![result](https://user-images.githubusercontent.com/50438750/132113167-ffd2733d-7d07-4aca-85fb-b2d12edaad8b.PNG)  


