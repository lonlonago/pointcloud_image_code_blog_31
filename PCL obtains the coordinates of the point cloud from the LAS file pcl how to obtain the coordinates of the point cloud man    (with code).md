 1. Calculate the formula to obtain the real coordinates 2. Directly obtain the real coordinates 3. Analog CC minus the offset value

#  I. Introduction 

##  1. Overview 

    PCL pcl :: Point XYZ is a data structure used to store point cloud xyz coordinates, where x, y, z are data of type float. The source code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574169133
  ```  
    The point cloud coordinates in the point record of the LAS file are stored as X, Y, Z, Scale, Offsets. Therefore, to obtain the coordinates of the point cloud from the LAS file, simply save the real values in the LAS file to the pcl :: Point Cloud < pcl :: Point X Y Z > container. 

##  2. Get the real coordinates of the point cloud from las 

    Obtain the real coordinates of the point cloud from the las point cloud. Currently, there are two ways to implement it in laslib: Method 1: Calculate and obtain according to the calculation formula: where,,, are the recorded values in the Li-DAR point cloud data. The corresponding implementation code is: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574169133
  ```  
 Method 2: Obtain directly: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574169133
  ```  
 In CloudCompare, the las point cloud with large coordinate values will subtract the offset to convert the coordinates, which is the function realized by the operation shown in the following figure: 

 ![avatar]( b744a0ecac3442a1b4c939c359f6ded7.png) 

  For this operation, I also wrote a simple implementation code: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574169133
  ```  
 In summary, this article gives three codes to get PCL :: Point XYZ from LAS files 

#  Code implementation 

##  1. Calculate the formula to obtain the real coordinates 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574169133
  ```  
##  2. Directly obtain the real coordinates 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574169133
  ```  
##  3. Analog CC minus the offset value 

>  It is important to note here that when no offset value is provided in the las header file or the offset value provided is small, the CloudCompare software is more intelligent and will automatically calculate an appropriate offset, while the code simply reads the offset value from the las header file. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574169133
  ```  
