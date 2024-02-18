#  First, the principle of the algorithm 

##  1. Definition of DoN 

 ![avatar]( 20210208092728157.png) 

   Difference of Normals Based Segmentation According to the difference of normal vector characteristics at different scales, using PCL-like :: DifferenceOfNormalsEstimation to realize point cloud segmentation, the point cloud segmentation effect is better in dealing with scenes with large scale changes, and using different support radii to estimate two units of the same point. 

##  2. DoN algorithm 

 ![avatar]( 20200727164719382.png) 

   The DoN feature originates from the observation that the normal vector of the surface based on the given radius estimate can reflect the inherent geometric characteristics of the surface. Therefore, this segmentation algorithm is based on normal estimation, and needs to calculate the normal estimation of a certain point in the point cloud. Neighborhood information is usually used when calculating the normal estimation, and it is obvious that the choice of neighborhood size will affect the result of the normal estimation. In the DoN algorithm, the size of the neighborhood selection is called the support radius (support radius). Select different support radii for a certain point in the point cloud, that is, different normal estimates can be obtained, and the difference between the normals is the normal difference.  

##  3. DoN segmentation steps 

 ![avatar]( 2021020809284530.png) 

 (1) For each point in the input point cloud data, use the larger support radius rl to calculate the normal vector; (2) For each point in the input point cloud data, use the larger support radius rs to calculate the normal vector; (3) For each point in the input point cloud data, unify the normal vector difference of each point (4) Filter the resulting vector domain (DoN eigenvector) to segment the point cloud corresponding to the target size. 

##  4. References 

>  [1] doc： Difference of Normals Based Segmentation [2] PCL：pcl::DifferenceOfNormalsEstimation 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150325
  ```  
#  III. Display of results 

 ![avatar]( 202007271625083.png) 

##  1. Normal visualization results 

 ![avatar]( 20200727162520533.png) 

##  2. Visualization of corresponding curvature information 

 ![avatar]( 20200727162620807.png) 

##  3. Visualization using curvature classification results 

 ![avatar]( 20200727162655622.png) 

##  4. European clustering segmentation results 

 ![avatar]( 20200727162742590.png) 

