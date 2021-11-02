# COVID19-Classification-of-pneumonia-cases
In this assignment we created a dataset and a costum model for classification of pneumonia cases. We tried two types of classification - coarse classification to 3 classes (Bacterial, Viral, Fungal), and fine classification to each of the genus/specesies type of pneumonia.

## The dataset
The data consists of X-ray images of pneumonia cases gathered from different sources. The data is updated on an almost daily basis.

![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/data1.png)
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/data2.png)
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/data3.png)
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/data4.png)

## Dealing with imbalanced data
In the assignment we dealt with imbalanced data. We explored several methods: First, when splitting the data we would like to have same the percentage of samples for each class. For example, for label with only 30 occurrences we wouldn’t want that all 30 occurrences will be in the training \ testing data. So for splitting the data we used StratifiedShuffleSplit method which returns stratified and shuffled sets. 

![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/histogram.png)
As we can see, we got the same Distribution !

Second, to deal with imbalance data We observe 3 methods , all methods was preformed solely on train data:

**Oversampling:** we added more copies of the minority classes by duplicate them . After getting results from the model when using over-sampled data the model guessed only label 1 so we figure out that that we may have same distribution but the other labels has many duplicated so the model was still over-fitted to match all labels as the majority class so will present the algorithm we did but we will continue with other method .

The data ufter oversampling:

![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/over_sampled.png)


**Undersampling:** we thought about sample only 20 samples of “Viral” label so we get similar distribution but 20 samples out of 120 mean through away a lot of information and we did not want it .

**Class weights:** we want that the training algorithm will consider the skewed distribution of the classes, without change the data itself. This can be achieved by giving different weights to both the majority and minority classes. The difference in weights will influence the classification of the classes during the training phase. The whole purpose is to penalize the misclassification made by the minority class by setting a higher-class weight and at the same time reducing weight for the majority class.

## Results 
### Coarse
#### Loss and Accuracy
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/model_acc.png)
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/model_loss.png)
#### Confusion matrix
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/conf_mat.png)

#### Recall and percision

|                   | label 0       |label 1       |  label 2     |
| -------------     | ------------- |------------- |------------- |
| recall score      | 0.2           |     1        |      0.5     |
| precision score   |        1      |   0.833      |     1         |
### ROC and AUC
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/ROC.png)
### Fine
#### Loss and Accuracy
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/model_acc2.png)
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/model_loss2.png)
#### Confusion matrix
![](https://github.com/shaniklein/COVID19-Classification-of-pneumonia-cases/blob/main/images/conf_mat2.png)
