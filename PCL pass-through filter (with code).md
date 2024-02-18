 + 1. Algorithm principle 1. Main function 2. Remarks

 + 2. Code example 

 + 3. Results display 

 + 4. High-order usage 1. Obtain the index of the point 2. Filter multiple fields 3. Filter according to the intensity 4. Obtain points within a certain time range

#  First, the principle of the algorithm 

    The function of the pass filter is to filter out the points whose values are not within the given range in the direction of the specified dimension. The implementation principle is as follows: First, specify a dimension and the range under that dimension. Secondly, traverse each point in the point cloud to determine whether the value of the point on the specified dimension is within the range. Delete the points whose values are not within the range. Finally, the traversal is completed, and the remaining points form the filtered point cloud. The pass filter is simple and efficient, suitable for operations such as eliminating background. 

>  PCL in the PCL :: Pass Through class to achieve a given user point cloud field is limited, the point cloud for simple basic filtering, such as point cloud filter limit all Z field is not within a certain range of points, the use of this class is more flexible but completely depends on the user's qualified fields and corresponding conditions. 

##  1. Main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574214360
  ```  
>  Sets the name of the qualified field string field_name, such as "x", "y", "z", "intensity", etc. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574214360
  ```  
>  Sets filter restrictions, including minimum limit_min and maximum limit_max. This function is used with setFilterFieldName () for all points in the point cloud. Points where the value of the field set by setFilterFieldName () is not outside the range set by the user will be deleted. The parameter limit_min is the minimum value of the allowed range, which defaults to DBL_ MIN, limit_ max is the maximum value of the allowed range, which defaults to DB L_MAX. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574214360
  ```  
>  Set whether the point outside the filter restriction is an internal point, limit_negative the default value is false, and the output point cloud is a point set within the set range of the set field. If it is set to true, it is just the opposite. Note: In PCL1.11.1 version, the setNegative () function is used instead. 

##  2. Remarks 

>  If the point cloud is collected by line structured light scanning, the object must be widely distributed along the z direction, but the distribution in the x and y directions is within a limited range. At this time, a pass filter can be used to determine the range of the point cloud in the x or y direction, which can quickly cut off outliers and achieve the purpose of coarse processing in the first step. 

#  Code example 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574214360
  ```  
#  III. Display of results 

 ![avatar]( 0198210789514c4cbbbc875d1fc77192.png) 

#  IV. Advanced usage 

##  1. Get the index of the point 

   Setting the default parameter of the passthrough filter object to true can be used to obtain the indices of points both within and outside the given range. As follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574214360
  ```  
 Code example 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574214360
  ```  
##  2. Filtering multiple fields 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574214360
  ```  
##  3. Filter according to intensity 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574214360
  ```  
##  4. Acquire points within a certain time frame 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574214360
  ```  
>  MyPointCloud.h, MyPointCloud.cpp See: PCL extracts scan lines according to time index 

 ![avatar]( d32f522d8c69494e975cd90070847156.png) 

