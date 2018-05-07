# Implementation of Seam Carving
Project for CS766 (Computer Vision), Spring 2018 UW-Madison

## Team Members
- Shuo Sun, ssun99@wisc.edu
- Shilu Zhang, szhang256@wisc.edu

## Project Proposal
[Link to Google Doc](https://docs.google.com/document/d/1z0z4b6yVGYcPRXuUE_9kr-a2so3J8vSAw8htgIIx6CU/edit?usp=sharing)


## Results
### 1. Aspect ratio change

![Original Input](Images/christmas_original.jpg=207 × 130)
![Original Input with vertial seams](Images/christmas_rm_100cols_Vseams.png)
![Seam Carving](Images/christmas_rm_100cols.png)

### 2. Retargeting with Optimal Seams-Order

![Original Input](Images/charles_original.png)

![(A) Remove horizontal seams first and then remove vertical seams](Images/charles_rm100rows_rm100cols.png)
![(B) Remove vertical seams first and then remove horizontal seams](Images/charles_rm100cols_rm100rows.png)
![(C) Alternate between horizontal and vertical seams](Images/charles_rm100rows_100cols_altern.png)
![(D) Optimal order retargeting](Images/charles_optimal_100cols100rows.png)

### 3. Image Enlarging

![Original Input](Images/desert.jpg)
![Original Input with vertial seams](Images/desert_add_50percentcols_Vseams.png)
![Seam Carving](Images/desert_add_50percentcols.png)

### 4. Content Amplification

![Original Input](Images/arch_original.png)
![Resizing](Images/arch_magnified.png)
![Seam Carving](Images/arch_retarget.png)

### 5. Object Removal

![Original Input](Images/Couple.png)
![Mask](Images/Couple_protect_mask.png)
![Object Removed](Images/Couple_objrm.png)

### 6. Object Removal and Resize

![Original Input](Images/Beach.png)
![Girl Removed](Images/Beach_girl_removed.png)
![Girl Removed and Resized](Images/Beach_girl_removed_resized.png)


### 7. Forward Energy vs Backward Energy

The original algorithm using Backward Energy choose to remove seams with the least amount of energy from the image, ignoring energy that are inserted into the retargeted image. The new algorithm in the Rubinstein et al paper looks forward at the resulting image and searchs for the seam whose removal inserts the minimal amount of energy into the image. 
![Forward Energy](Images/ForwardEnerge.png)

The cost is measured as forward differences between the pixels that become new neighbors. We use these costs in a new accumulative cost matrix M to calculate the seams using dynamic programming. Here is the formula for vertical seams. P(i, j) is an additional pixel based energy measure.

Here is an comparison between the original seam carving backward energy (middle) and the new forward energy (right) for resizing an image. The new results suffer much less from the artifacts generated using backward energy such as the difference in water color and the distortions of the bench bars and skeleton.

![Original Input](Images/bench3.png)

![BackWard Energy](Images/bench_rmVseams_be.png)
![ForWard Energy](Images/bench_rmVseams2_fe.png)

![BackWard Energy](Images/bench_rm_be.png)
![ForWard Energy](Images/bench_rm2_fe.png)


### 8. Simple Video Seam Carving


## Discussion
