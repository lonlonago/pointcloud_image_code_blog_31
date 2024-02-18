#  First, the main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957415642
  ```  
 createViewPort (): is a function used to create a new viewport. The required four parameters are the minimum value of the viewport in the X-axis, the minimum value of the Y-axis, the maximum value of the X-axis, and the maximum value of the Y-axis, with values ranging from 0 to 1. 

#  Code implementation 

##  1. Two small windows to visualize point clouds 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957415642
  ```  
  result display  

##  2. Three small windows to visualize point clouds 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957415642
  ```  
 result display  

##  3. Four small windows to visualize point clouds 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957415642
  ```  


--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  Introduction to the algorithm 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574228549
  ```  
 PCL :: registration :: CorrespondenceRejectorSurfaceNormal implements a simple method of removing the corresponding relationship based on the normal angle of the corresponding point. 

##  1. Main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574228549
  ```  
##  2. References 

>  Sun Peiqi, Bu Junzhou, Tao Tingye, Fang Xingbo, He Han, Feng Jiaqi. Point cloud registration algorithm based on normal vector of feature points [J]. Bulletin of Surveying and Mapping, 2019 (08): 48-53. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574228549
  ```  
#  III. Display of results 

 ![avatar]( 20210323211130662.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview 

   Class pcl :: Normal Refinement < NormalT > This class optimizes the normal vector of a known point by iteratively updating the normal vector of each point to the average of all normal vectors in its neighborhood. The purpose of this is to use the same point correspondence when estimating the original normal vector to avoid repeating the nearest neighbor search. 

>  The official website mentions the weighted average. At present, the weight coefficient in the source code is 1, so only the average of the normal vector is calculated. 

##  2. References 

 pcl::NormalRefinement< NormalT > Class Template Reference 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574281260
  ```  
#  III. Display of results 

 ![avatar]( 77a76e5abfc04901a8cb09cf785d5880.png) 



--------------------------------------------------------------------------------

 + 1. LAS Overview 1. Common Header 2. Variable-length Record

 + 2. Code implementation 1. MyPointCloud.h2, MyPointCloud.cpp3, main.cpp

 + 3. Results display 

#  Overview of LAS 

##  1. Public head 

   The common header is used to record the basic information of the dataset, such as the total number of Li-DAR points, the data range, the Li-DAR point format, the total number of variable-length records, etc. Since a LAS file may be directly generated from the data collected by the hardware or obtained after extracting, fusing, and modifying the existing data, the common header also records the generation method of the LAS file. For the characteristics of multiple returns of Li-DAR data, the common header also records the total number of Li-DAR points returned each time up to 5 returns. The common header also records the scale factor (scale) and offset value (offset) in the X, Y, and Z directions, which can reduce the length of each point record (Li-DAR point set records use the long type to record three-dimensional coordinates), and the true coordinates of Li-DAR point cloud data can be obtained by the following formula: where,, is the recorded value in the Li-DAR point cloud data. 

##  2. Variable length records 

   The variable-length record area is located after the public file header. The projection information, metadata information and user-defined information used to record data are the most flexible parts of the LAS format. Each variable-length record includes a fixed variable-length record head and a flexible extended domain. The length of a variable-length record = the length of the variable-length record head + the length of the extended domain. It contains some metadata, such as the coordinate system information of the point cloud data, the record label used to determine the starting position of each variable-length record, and the user ID of the variable-length record and the record ID determined by the LAS format. The point set record part saves a large amount of Li-DAR pin point information, which is the core of the LAS file, and records the three-dimensional coordinates and related attributes of each discrete point cloud. There are 100 Li-DAR point record formats supported by LAS, from Format 0 to Format 99. In the same LAS file, there is only one Li-DAR point format. And it must be consistent with the point format in the common header. Format 0 is the basic Li-DAR point record format, and other point formats are extended on the basis of Format 0. For example, the commonly used Format 1 format adds an attribute on the basis of Format 0 to record the GPS time of each pin point. This ensures the flexibility and extensibility of attribute records in the Li-DAR point format. The point record in Format 0 format contains a number of basic properties, such as spatial X, Y, Z coordinates, laser reflection intensity value, classification number of the current point, total number of echoes of the current laser pulse, the current pin point belongs to the first return, etc. Considering the characteristics of Li-DAR scanning by strip, the point record in Format 0 also includes information such as the current laser scanning angle and whether the current point is a strip edge point (the recording of this information helps to match and splice data between strips in subsequent processing). At present, LasiLib has been updated to LAS version 2.0.+, and LAS has gradually become an industry standard for Li-DAR data processing. 

#  Code implementation 

##  1、MyPointCloud.h 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574181336
  ```  
##  2、MyPointCloud.cpp 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574181336
  ```  
##  3、main.cpp 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574181336
  ```  
#  III. Display of results 

 ![avatar]( ed354fede1864b719e426641203db2f1.png) 



--------------------------------------------------------------------------------

#  Introduction to the algorithm 

   PCL :: registration :: CorrespondenceEstimation, is to find the correspondence between the base class, when the input is < pcl :: Point XYZ > data type, is based on the correspondence between the point search, when the input is a feature descriptor, is based on the feature descriptor correspondence lookup. 

##  1. How to use 

 Taking the correspondence search based on the FPFH feature descriptor as an example, the code is written as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574299991
  ```  
>  Simply change the default data type pcl :: Point XYZ to pcl :: FP FH Signature 33. The same applies to other types of feature descriptors. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574299991
  ```  
#  III. Display of results 

 ![avatar]( 20210407145050904.png) 



--------------------------------------------------------------------------------

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


--------------------------------------------------------------------------------

#  I. Overview 

    To output content to text, use the class ofstream to implement it. The specific steps are as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574257454
  ```  
 Now provides a complete program to achieve the point cloud master curvature information into the txt file save. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574257454
  ```  
#  III. Display of results 

 ![avatar]( 59e07356c927420abde0803b6586c96b.png) 

#  IV. Reference link 

 C++ how to output input to a text file 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#   code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574166261
  ```  
#  III. Display of results 

 ![avatar]( 20210420204715897.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Fitting overview 

   B-spline curve is the main curve representation method used in the field of Computer-Aided Design (CAD), and has become the standard for representing curves in this field. The definition of sub-B-spline curve is as follows: where, is the control point, is the sub-B-spline basis function defined on the node vector. And curve fitting refers to the use of continuous curves to approximately describe or compare the functional relationship between coordinates represented by discrete points. It is a method of approximating discrete data with analytical expressions. When the type of curve used is a B-spline curve, it is called B-spline curve fitting. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574137089
  ```  
#  III. Display of results 

 ![avatar]( 2020072417122810.png) 

#  IV. Implementation methods 

##  1. Parameter settings 

>  Enter point cloud data and curve fitting in command line arguments 

 ![avatar]( 20200724171438183.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

 ![avatar]( 1bb70f329010428d85e414e225831f9c.jpeg) 

    Known polygonal point set, its arrangement order is messy, connect the points in turn, unable to form a definite polygon, need to sort the point set, and then draw the polygon. In the process of point set sorting, it mainly lies in the determination of the size relationship of the points.  

    The steps of the algorithm for sorting counterclockwise are as follows: Definition: The point is in the counterclockwise direction of the point, then the point is greater than the point 1. Calculate the center of mass O of the point set, with the center of mass as the center point of the counterclockwise rotation. 2. Calculate the size relationship between the points. The calculation of the size relationship can be calculated according to the definition of the vector cross product. If the cross product of the vector sum is greater than 0, then the vector is in the counterclockwise direction of the vector, that is, the point is less than the point. 

    The algorithm steps for sorting clockwise are as follows: Definition: The point is in the counterclockwise direction of the point, then the point is greater than the point 

 1. Calculate the center of mass O of the point set, with the center of mass as the center point of the counterclockwise rotation. 2. Calculate the size relationship between the points. The calculation of the size relationship can be calculated according to the definition of the vector cross product. If the cross product of the vector sum is less than 0, then the vector is in the clockwise direction of the vector, that is, the point is greater than the point. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574145284
  ```  
#  III. Display of results 

 ![avatar]( 60ad55faceba4e89bcc6eab43d606dd9.png) 

 ![avatar]( 23876776c3e848c0b3e0c70cadf4b028.png) 

  Sort counterclockwise, sort clockwise  

#  IV. Reference link 

 [1] 【计算几何】多边形点集排序 [2] for clever101 [3] 逆时针排列无序点集 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Overview of algorithms 

##  1. Evenly distributed 

   In probability theory and statistics, a uniform distribution, also known as a rectangular distribution, is a symmetric probability distribution in which the probability of a distribution at the same length interval is equally likely. The uniform distribution is defined by two parameters, a and b, which are the minimum and maximum values on the number line, usually abbreviated as. 

#  PCL built-in functions 

##  1. Main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217556
  ```  
##   2. Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217556
  ```  
##   3. Display of results 

 ![avatar]( 5d70404aa4b849b99c1190e8d2ea47ba.png) 

#  C++ std function 

##  1. Main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217556
  ```  
>  For more detailed analysis, see: std :: uniform_int_distribution 

##   2. Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574217556
  ```  
##   3. Display of results 

 ![avatar]( d5ad4e5ed3ce44faa09e6dddfcd5b082.png) 



--------------------------------------------------------------------------------

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


--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  Introduction to the principle 

   The cylindrical neighborhood search is an extended application of the KD-tree algorithm in point cloud data processing, and has unparalleled advantages in some specific scene applications. Its main principle is to project the point cloud onto a specified plane, then perform a circular neighborhood search based on the plane, and then backproject the search results back to get the point cloud in the cylindrical neighborhood. The following example code, knowing the coordinates of a point on the trunk, performs a cylindrical neighborhood search on the point, and can roughly extract the trunk. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957425112
  ```  
#  III. Display of results 

 ![avatar]( 720a4c6a22b14a6686cb3bf2246c0fe7.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

