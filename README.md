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

![alt text](https://github.com/charanya78/melanoma-detection/blob/main/diagrams/ARCH_DIAG.PNG)

#### BASELINE CNN


#### VARIANCE SCORE AND CREATION OF NEW DATASET


#### PRE PROCESSING

![alt text](https://github.com/charanya78/melanoma-detection/blob/main/diagrams/data_aug.PNG)

#### CNN FEATURE EXTRACTION


#### ABCD FEATURE EXTRACTION

![alt text](https://github.com/charanya78/melanoma-detection/blob/main/diagrams/abcd.PNG)

#### FEATURE FUSION AND FINAL CLASSIFICATION 


## REPOSITORY STRUCTURE



## EXECUTION 


