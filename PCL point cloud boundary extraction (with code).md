#  First, the principle of the algorithm 

##  1. Algorithm overview 

>  Point Cloud Boundary Extraction Based on Normal: PCL :: Boundary Estimation 

##  2. Detailed process 

   The edge points of the 3D point cloud are often located at the outermost periphery, and the points around the edge points are mostly on the same side of the edge points. The process of judging the edge point set of the point cloud is as follows: 

 ![avatar]( 20210307175730472.png) 

   It can be found that it is the angle between two adjacent vectors. As shown in the figure below, arrange the elements in the set in descending order to find the largest angle among them. When it is greater than the threshold (taken in the code), the point is considered an edge point.  

##  3. References 

>  [1] Wang Shaochen. Research on the measurement method of workpiece curved surface contour based on point cloud reconstruction technology [D]. Shandong University, 2020. P36-38 [2] Song Tao, Cao Libo, Zhao Mingfu, Liu Shuai, Luo Yuhang, Yang Xin. Registration and optimization algorithm of key points in 3D point cloud [J]. Advances in Laser and Optoelectronics, 2021, 58 (4): 0415008 [3] Cheng Xiaojun, Jia Dongfeng, Cheng Xiaolong. Theory and Technology of Massive Point Cloud Data Processing [M]. Shanghai: Tongji University Press, 2014. P 68-69 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574157592
  ```  
#  III. Display of results 

 ![avatar]( 20210210215256223.png) 

>  Red is the original point cloud, and green is the boundary point. 

