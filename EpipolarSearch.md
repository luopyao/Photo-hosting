# Epipolar Search

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

## Introduction
Epipolar Search is a method searching correspondences from one frame to the other. For points on the reference frame, the method searches along the epipolar line on the current frame to find the point with the best score and define the correspondence.For pixels which can't be extracted discriptors , we can use epipolar search to find correspondences.

## Evaluation
### Based on ORB Matches
The experiments below show the result of epipolar search on both MH_02_easy and MH_03_medium sequences in Euroc dataset. The experiments first define one frame as the reference frame and the ORB matches between two frames which are 6 frames apart as ground truth. Then the correspondences based on the ORB features are found and optimized. The depth of reference points are computed by triangulation. Finally ,according to the depth, points are projected on the frame 18 frames apart.



The table below shows the result of final correspondences and project correspondences in different scenes in MH_02_easy. In final matches, the yellow points mean the immature points found by only epipolar search and the green points mean the optimized points after optical flow.

![ORB_MH02_Result](https://raw.githubusercontent.com/luopyao/Photo-hosting/master/images/ORB_MH02_Result.png)


The table below shows 3 kinds of L2 norm error. 
![ORB_MH02_Error](https://raw.githubusercontent.com/luopyao/Photo-hosting/master/images/ORB_MH02_Error.png)


The table below shows the overall goodness of searching process in MH_02_easy. We consider the searching is good when the final matching ratio after optical flow satisfies the condition.The higher the ratio, the better the searching process in the sequence.
![ORB_MH02_Ratio](https://raw.githubusercontent.com/luopyao/Photo-hosting/master/images/ORB_MH02_Ratio.png)

The same experiment on MH_03_medium.
![ORB_MH03_Result](https://raw.githubusercontent.com/luopyao/Photo-hosting/master/images/ORB_MH03_Result.png)

![ORB_MH03_Error](https://raw.githubusercontent.com/luopyao/Photo-hosting/master/images/ORB_MH03_Error.png)
It is worth mentioning that, uncorrect matches in ground truth which is obtained by the ORB matches may bring large error.This situation can be seen in the yellow highlight block. 
![ORB_MH03_Ratio](https://raw.githubusercontent.com/luopyao/Photo-hosting/master/images/ORB_MH03_Ratio.png)


### Global Searching
Different from the experiments before, we perform epipolar search on the whole image.Without detecting ORB matches as ground truth,we only record the number of matches.

![GLOBAL_MH02](https://raw.githubusercontent.com/luopyao/Photo-hosting/master/images/GLOBAL_MH02.png)

![GLOBAL_MH03](https://raw.githubusercontent.com/luopyao/Photo-hosting/master/images/GLOBAL_MH03.png)



