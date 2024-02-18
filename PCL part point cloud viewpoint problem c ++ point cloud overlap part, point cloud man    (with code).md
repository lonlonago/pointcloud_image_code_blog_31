#  I. Overview of the problem 

   Aiming at the point cloud in pcd format processed by CloudCompare software, the final results show that the point cloud position deviation is large in the experiments of feature point extraction and registration using PCL. This blog gives a solution. 

#  Second, the solution 

   The pcd format point cloud data processed by PCL, the default viewpoint is: VIEWPOINT 0 0 0 1 0 0 0 0 The pcd format point cloud data processed by CloudCompare software, the saved viewpoint is: VIEWPOINT 0 0 0 0.707107 -0.707107 0 0 So when using PCL display, the position of the point cloud will change, resulting in the display position and the actual position of the point cloud does not match. Therefore, the viewpoint of the pcd format point cloud data processed by CloudCompare software is changed to: VIEWPOINT 0 0 0 0 0 0 0 0 0 0 to solve the problem of position inconsistency. 

##  1. Software implementation 

 Save the point cloud in pcd format processed by CloudCompare software to las format, and then save the point cloud in las format to pcd format. 

 ![avatar]( 15030baa686b454a8102601a1c84b858.png) 

##  2. Code implementation 

 Load the point cloud with PCL - > Save it as an ASCII point cloud - > Notepad to open the pcd file - > Change the value of VIEWPOINT to 0 0 0 1 0 0 0. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957421155
  ```  
 ![avatar]( 6859d47ed3a74ddf8e55879c69fccfa3.png) 

 After saving as ASII, it can be opened with txt text, and the following line can be changed to the figure:  

 The way of using software operation is simple and easy to implement without errors, and the use of code operation can more intuitively demonstrate its implementation principle. 

#  III. After adjustment 

 ![avatar]( 3607b6d11ff54a5db3ffb3698b02bbeb.png) 

