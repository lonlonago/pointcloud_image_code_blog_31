#  First, the principle of the algorithm 

##  1. Introduction to the principle 

 ![avatar]( 20210122094128664.png) 

   NormalSpaceSampling is: normal space sampling, which is sampled uniformly and randomly in the normal vector space, so that the normal distribution between the selected points is as large as possible. The result is that there are more remaining points where the feature changes greatly, and there are few remaining points where the change is small, which can effectively maintain the feature. The motivation of this strategy is to observe that for some scenarios (such as the "cutting plane" dataset), the small features of the model are crucial to determine the correct alignment. Strategies like random sampling usually only select a few samples in these features, which results in some parts not being able to determine the correct rigid body transformation. Therefore, one way to increase the likelihood that sufficient constraints exist to determine the transformation of all components is to store points based on the normal positions in the angular space, and then sample over these storage points as uniformly as possible. Therefore, normal space sampling is a very simple example of alignment using surface features; this method has lower computational cost compared to traditional feature-based methods, but is less robust.  

 ![avatar]( 20210122094139302.png) 

   For scenes with a good normal distribution, an accurate sampling strategy is not critical. However, the "cutting plane" scene only converges with normal spatial sampling. The reason is that samples that are not in the trench only help determine three of the six components of the rigid body transform (one translation and two rotations). The other three (two translations and one rotation in the plane) are determined entirely by the samples within the notch. The random uniform sampling strategy places only a small number of samples in the trench (a). This, combined with noise and distortion in the rest of the plane masking the effects of those pairs sampled from the trench, illustrates why uniform and random sampling does not converge to the correct alignment. Instead, normal spatial sampling selects more samples in the trench (b).  

##  2. Function analysis 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 empty constructor 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 destructor 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 Sets the number of indexes to sample. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 Get the number of indexes to sample. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 Sets the seed point of the random function. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 Get the seed parameter of the random function. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 Set the number of X. Y and Z rays binsx, binsy, and binsz respectively. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 The number of X, Y and Z direction rays binsx, binsy and binsz were obtained respectively. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 Sets the normal from the input point cloud. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
 Obtain the normals obtained through the input point cloud. 

##  3. References 

>  [1] Yan Li, Tan Junxiang, Liu Hua, Chen Changjun. Ground and vehicle laser point cloud registration fusing genetic algo and ICP [J]. Journal of Surveying and Mapping, 2018, 47 (04): 528-536. [2] S. Rusinkiewicz and M. Levoy, "Efficient variants of the ICP algorithm," Proceedings Third International Conference on 3-D Digital Imaging and Modeling, Quebec City, Quebec, Canada, 2001, pp. 145-152, do i: 10.1109/IM.2001.924423. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574266146
  ```  
#  III. Display of results 

 ![avatar]( 20210122100445836.png) 

