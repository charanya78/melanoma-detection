# Melanoma Detection

## DESCRIPTION 

The objective of this project is to develop a two-tier convolution neural network for malignant melanoma prediction. The baseline CNN identifies the challenging samples to a new dataset. For the challenging samples to be identfied, a cross variance score is proposed. The samples in the new dataset are subject to hair removal techniques and data augmentation. These samples are passed to another CNN to extract CNN features and ABDC features based on the melanoma rule are also extracted. These features are fused and machine learning classifiers are used to predict the presence of melanoma in that image.

## SOFTWARES USED

Jupyter Notebook - Implementation

## LANGUAGE USED

Python

## DEPENDENCIES NEEDED

- scipy
- tensorflow
- keras
- sklearn
- imageio
- cv2
- matplotlib
- skimage
- PIL 
- seaborn

To install the above mentioned dependencies use:

- pip install scipy
- pip install tensorflow
- pip install keras
- pip install sklearn
- pip install imageio
- pip install pandas
- pip install numpy
- pip install cv2
- pip install matplotlib
- pip install skimage
- pip install PIL
- pip install seaborn

## ARCHITECTURE DIAGRAM

The major parts in the project are First-Tire CNN, Challenging dataset creation, Second-Tier CNN feature extraction, Extraction of asymmetry, border, color and diameter (ABCD) Feature and Classification with 2-HDCNN features.

![alt text](https://github.com/charanya78/melanoma-detection/blob/main/diagrams/ARCH_DIAG.PNG)


#### DATASET

#### BASELINE CNN

- In the first tier of classification, the Baseline CNN classifies the data samples and extracts the challenging samples. 
- The probability difference of a lesion being benign and malignant is computed as class probability variance score and the threshold of this score is calculated. 
- For every sample, CPVS score is calculated and if it is lesser that the threshold, these samples are classified as challenging and are sent to a baseline segregated dataset (BSD).
- There are four convolution blocks in the CNN architecture where each block consists of different combinations of Convolutional layer, batch normalization layer, Max pooling layer and dropout layer. 
- After these blocks, there are flattened, Dense, and Dropout layers. 
- Code : https://github.com/charanya78/melanoma-detection/blob/main/1.%20CNN.ipynb

#### VARIANCE SCORE AND CREATION OF NEW DATASET

- The probability of a sample being benign and the probability of the same sample being malignant are found along with the predicted class and true class. 
- The class probability variance score which is the difference between the probability of a sample being benign and the probability of a sample being malignant is calculated. 
- When the confidence factor is less than 0.999995,  the error ratio (the ratio between the number of misclassified samples and the total number of samples in the range) is 0.05 which means 95% of the time, it predicts accurately. 
- On further analysis, it was found that, as the confidence factor decreases from 0.99, the number of misclassified samples increases and the error ratio increases to 0.3 which means that only 70% of the time, it predicts accurately. 
- Different values of the threshold value are tried through trial and error and it is found as 0. 999995. 
- These challenging samples (confidence factor < 0.999995) are moved to a segregated dataset. 
- Code : https://github.com/charanya78/melanoma-detection/blob/main/1.%20CNN.ipynb

#### PRE PROCESSING

- Hair is removed from the lesions to ease the classification process. 
- The image is converted to a grayscale and then it is passed to a Blackhat filter. 
- The Blackhat filter enhances the dark regions of interest in a much bright background in this case the hair is the dark region which is in a bright background (the lesion itself). 
- This algorithm returns an image with the hair highlighted. 
- This image is then passed to a thresholding technique. 
- Here an image where only the hair is highlighted in a black background is formed. 
- Finally, the inpainting algorithm is applied to this image. 
- The original image with hair is passed along with the masked image where the hair is highlighted (output of thresholding).
- The masked regions are removed from the original image and it results in an image with the hair removed.
- Code - https://github.com/charanya78/melanoma-detection/blob/main/2.%20Hair%20removal.ipynb

![alt text](https://github.com/charanya78/melanoma-detection/blob/main/diagrams/hair.PNG)

- Data augmentation processes like random rotation, random noise and horizontal flipping are performed to balance the dataset. 
- Random rotation rotates the image between 25% to the left and 25% to the right. 
- The flip function directly flips the image array. 
- For the random noise function, the type of noise chosen is Gaussian and the amount of noise added is kept to 0.05 to not change the image drastically.
- Code - https://github.com/charanya78/melanoma-detection/blob/main/3.%20Data%20Augmentation.ipynb 

![alt text](https://github.com/charanya78/melanoma-detection/blob/main/diagrams/data_aug.PNG)
 
#### CNN FEATURE EXTRACTION


#### ABCD FEATURE EXTRACTION

![alt text](https://github.com/charanya78/melanoma-detection/blob/main/diagrams/abcd.PNG)


#### FEATURE FUSION AND FINAL CLASSIFICATION 



## EXECUTION 


