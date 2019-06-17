# stanford_cars
Stanford cars dataset prediction with fastai.v1. The main idea is using box in the train data and segmentation process to crop the image, so the model can learn better. 

This repo take https://github.com/mazenmel/Stanford-Car-Dataset/blob/master/stanfordCars.ipynb as the structure. The MaskRCNN https://github.com/matterport/Mask_RCNN was used to generate segmented car

### With cropped train data + segmented train data (MaskRCNN)
Overall accuracy: 77.07 % (on cars_test data)

Take-away points:
- Cropping and segmenting dataset can't improve the accuracy from baseline (mazenmel repo).
