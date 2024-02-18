#  I. Overview of algorithms 

##  1. Definition of Gaussian noise 

   The Gaussian distribution, also known as the normal distribution, is denoted as the parameters of the distribution, which are the expectation and variance of the Gaussian distribution, respectively. When there is a definite value, it is also determined that the distribution, especially when, is the standard normal distribution. The so-called Gaussian noise refers to a type of noise whose probability density function obeys the Gaussian distribution (i.e. normal distribution). Note that in the generation of simulated measurement point clouds, this noise is only equivalent to moving an existing point by one position, rather than adding new points. 

#  PCL comes with functions 

##  1. Main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248074
  ```  
   The underlying implementation is still based on the random library of C++ 11, but since it can be used as a call function in PCL alone, this method should be the best choice for point clouds. 

##  2. Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248074
  ```  
##  3. Display of results 

 ![avatar]( 85d8a33ef1924efcaf564b1821ef28b5.png) 

#  Second, based on the Boost library 

##  1. Main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248074
  ```  
##  2. Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248074
  ```  
##  3. Display of results 

 ![avatar]( 20201109092604256.png) 

 Blue is the original point cloud data, red is the generated noise point, and Rabbit adds Gaussian noise with mean: 0 and standard deviation: 2mm.  

#  Implementation C++ STD 

##  1. Main function 

>  For more details, see: C++ normal_distribution Gaussian normal distribution function usage 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248074
  ```  
##  2. Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574248074
  ```  
##  3. Display of results 

 ![avatar]( dde5fa5ab7ce47d288384b8a9a391f10.png) 

