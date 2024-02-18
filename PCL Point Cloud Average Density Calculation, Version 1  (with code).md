##  First, the principle of the algorithm 

   Different sampling devices and different distances from the scene will cause differences in point cloud density. Existing methods for estimating point cloud density include distance-based methods and block-based methods. The distance-based average distance density representation method estimates the distribution density of point clouds by calculating the average distance of each point in the point cloud.

     The larger d is, the sparser the point cloud distribution and the smaller the density. Therefore, it is feasible to estimate the point cloud density by the average distance. 

##  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574290590
  ```  
##  III. Operational results 

 ![avatar]( 20200923183211815.png) 

##  四、pcl_isfinite 

 When using PCL for data processing, many algorithms will consider invalid points, which is mainly by determining whether the data members in the PointCloud class contain NaN. (1) pcl_isfinite function pcl_isfinite function returns a Boolean value to check whether a value is a normal value. Generally used in for loops and if continute. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574290590
  ```  
 (2) removeNaNFromPointCloud pcl :: removeNaNFromPointCloud (laserCloudIn, laserCloudIn, indices); The function has three parameters, namely the input point cloud, the output point cloud and the corresponding reserved index. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574290590
  ```  
