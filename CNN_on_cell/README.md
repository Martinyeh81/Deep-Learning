# Analyzed a cell whether is parasitized or not 

## Description
  Our problem is to Analyzed a cell whether is parasitized or not.
## Data

Parasitized

uninfected

## Problem
1. All sizes of images are different
2. Overfitting

## Preprocessing
### Size of image
we can find all the sizes of images are not the same, so we generate the mean of width and height. As a result, we can reshape all images to (130,130,3)
![shape](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Ridge_coef.png)

### Data Augmentation
In oreder to avoid overfitting, we adjust the angle, shift width and height, zoom the image and so on.
![change](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Ridge_coef.png)

## Result

### Loss and accuracy
||loss|acc|val_loss|val_acc|
| --- | --- | --- | --- | --- |
|0|0.889313|0.551366|0.689229|0.561154|
|1|0.678911|0.577691|0.677357|0.565000|
|2|0.676195|0.583340|0.679405|0.573846|
|3|0.677662|0.590432|0.664807|0.605000|
|4|0.672608|0.599046|0.661826|0.619615|
|5|0.662291|0.610265|0.671066|0.611538|
|6|0.445034|0.787924|0.238153|0.909231|
|7|0.213726|0.936614|0.214997|0.930000|
|8|0.185517|0.944587|0.177111|0.943462|
|9|0.174758|0.946590|0.165020|0.945385|
|10|0.173492|0.946991|0.173638|0.938462|
|11|0.170545|0.948313|0.204041|0.935000|

![change](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Ridge_coef.png)
![change](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Ridge_coef.png)

### Classification Report
||precision|recall|f1-score|support
| --- | --- | --- | --- | --- |
|0|0.94|0.93|0.94|1300|
|1|0.93|0.94|0.94|1300|

### Confusion Matrix
![change](https://github.com/Martinyeh81/The-Data-Incubator/blob/master/section_1/Image/LR_Ridge_coef.png)


## Conclusions
1. 

