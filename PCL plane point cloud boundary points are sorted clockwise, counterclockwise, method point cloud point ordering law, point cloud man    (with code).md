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

