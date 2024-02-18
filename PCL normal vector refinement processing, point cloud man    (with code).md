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

