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
...  
##Solve   
1. In all kinds of GAN methods, dedicated to generate images look like the image in the training dataset. However, these methods cannot generate images with some variety  
2. When the image is too less, GAN are difficult to generate images well  
3. When images have too many categories, the GAN methods will generate confusing images  
I give a example for the second and third points above  
We use the animal drawing images as the training dataset, there are more than 30 categories  
Training dataset sample  
![sample](https://user-images.githubusercontent.com/50438750/132112835-78de5b36-ea06-4092-a854-ef942d3945a4.PNG)

The StyleGAN2 generates messy images(The left side), the StarGAN2 generates overlapped images(The right Side)  


