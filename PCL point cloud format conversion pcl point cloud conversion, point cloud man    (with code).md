 + 1、pcd2ply 

 + 2、ply2pcd 

 + 3、pcd2obj 

 + 4 ▼ 2pcd 

 + 5、xyzrgb2xyz 

 + 6、pcd2txt 

 +7、txt2pcd 

 + 8、the2pcd 

 + 8.1 las to PointXYZ8.2 las to PointXYZI8.3 las to PointXYZL8.4 las to PointXYZRGB8.5 las to PointXYZGPSTime8.6 las to pcd (all attributes)

 + 9、stl2pcd 

 + 10 、 csv2pcd 

 + 11、pcd2png 

 + 12、vt2pcd 

#  1、pcd2ply 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
#  2、ply2pcd 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
#  3、pcd2obj 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
#  4 、 2pcd 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
>  When turning obj to pcd, first look at whether your obj format model has a color. If there is a color, use pcl :: Point XYZ RGB, and if there is no color, use pcl :: Point XYZ. The reason why FailFailed to find match for field'rgb '. Because there is no rgb information in the obj file, the point cloud to be converted uses the pcl :: Point XYZ RGB data format. 

#  5、xyzrgb2xyz 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
#  6、pcd2txt 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
#  7、txt2pcd 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
#  8、the2pcd 

 Las to pcd needs to use the laslib library. For the library distribution method, see: VisualStudio2019 Configuring LasLib Library under Win10 System 

##  8.1 las转PointXYZ 

 PCL gets the coordinates of the point cloud from the LAS file 

##  8.2 las转PointXYZI 

 PCL obtains the strength of the point cloud from the LAS file 

##  8.3 theivoPointXYZL 

 PCL gets the categorization label of the point cloud from the LAS file 

##  8.4 las转PointXYZRGB 

 PCL gets the color of the point cloud from the LAS file 

##  8.5 las转PointXYZGPSTime 

 PCL gets the GPS time of the point cloud from the LAS file 

##  8.6 las to pcd (full properties) 

 PCL gets all the properties of the point cloud from the LAS file 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
#  9、stl2pcd 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
#  10 、 csv2pcd 

 Test data: csv to pcd format point cloud test data 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
#  11、pcd2png 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
 The implementation converts ordered point clouds into images. When calling the savePNGFile function, if the third parameter is not filled in, it defaults to "rgb". Other available attribute information is: "normal", "label", "z", "curvature", and "intensity". 

 sample code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217104
  ```  
 ![avatar]( eef862af536b4c2bb160cac35ab19cd3.png) 

#  12、vt2pcd 

 ![avatar]( 26ef6130a17e4ee08763f94445d8bbc8.jpeg) 

 PCL.vtk file to .pcd  

