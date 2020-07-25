# Fashion classification

Main file: cfpd_cloth.ipynb
## Dataset
CFPD dataset: 19 cloth categories, 2500 images with people, multi label annotation of clothes

Also has segmentation info but not used in this project

## Task predict

Predict the labels of cloth for a given image. Usually multiple categories are presented (for example shoes, jeans, T-shirt, sunglasses, hat)


## Model

Pretrained MobileNetv2 was taken, won't be trained as dataset is small

4 feature layers were taken to form the top

Final layer was sigmoid of num_classes size, each neuron representing the probability of category in image

Loss: binary_croosentropy 

## Training

Adam, 20 epochs, lr = 0.002

## Results

auc score: 0.70 test/ 0.85 train

# Preprocessing labels

Initially labels are stores in .mat file, with a script to convert to json

For classification i convert it to csv table (index = image_id, columns = categories, 1 if category is at image)

The resulting file is category_01.csv

The script to convert json -> csv cfpd_pre.ipynb
