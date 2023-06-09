# Predict BMI values from face images

## Introduction 
While in-depth medical examination will give more definite answer to one’s health condition, there are other metrics that can be easily calculated which can also be used as health indicators. One of the most common metrics used is BMI, or Body Mass Index, which is derived from the mass, or weight, and height of a person. Specifically, the BMI is defined as the body mass divided by the square of height, which is expressed in kg/m2 unit. According do World Health Organizations (WHO), there are 5 categories, ranging from underweight to very severely obese. 

My goal in this project is to replicate and also extend the work of Kocabey et al. (2017) [[1]](#1). To the best of my knowledge, I will offer a brief summary of the work of the research. The group of authors built a BMI prediction system, which is composed of two stages: (1) deep feature extraction and (2) training a regression model. While I aim to reach the performance of their model, I have added in a few twists, specifically in how I process images for the training process. Note that the image dataset I received for this project is not exactly the same as that of the project above. However, the nature of the images is similar in the sense that they are obtained from people's profile with only face captured in order to make sure image quality is low. 

## EDA
The dataset I obtained consists of two parts: (1) 3,963 images in .bmp format and (2) a csv file with three columns (Human-reported BMI values, gender F/M, and image file name). In order to match the row with the image, I use CV2 library. Exact code can be found in (...) file. Below are some of my insights after looking at the dataset. 

### BMI categories proportion 

![Screen Shot 2023-06-08 at 10 03 55 PM](https://github.com/dangtr1910/bmi_prediction/assets/108795992/438db9a8-2005-4ee4-9c1e-c472f20821b7)

Note that while I define the range of BMI values in outliers group based on my judgement, other BMI categories follow the definition of WHO. In this plot, I want to point out that there is underpresentation in extreme cases in two ends (underweight and outliers). Specifically, there is no testing case for underweight group. Meanwhile, there is significantly more cases of outliers in testing dataset. I hypothesize that this will lead to lower accuracy when my model faces extreme cases. This statement proves to be correct in later testing stage. 

### Gender proportion 

## References
<a id="1">[1]</a> 
Kocabey, E., Camurcu, M., Ofli, F., Aytar, Y., Marin, J., Torralba, A., & Weber, I. (2017). Face-to-BMI: Using Computer Vision to Infer Body Mass Index on Social Media. Proceedings of the International AAAI Conference on Web and Social Media, 11(1), 572–575. https://doi.org/10.1609/icwsm.v11i1.14923
