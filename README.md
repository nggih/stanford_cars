# stanford_cars
Stanford cars dataset prediction with fastai.v1. The main idea is using box in the train data and segmentation process to crop the image, so the model can learn better as it focus only on the targeted car. 

This repo take https://github.com/mazenmel/Stanford-Car-Dataset/blob/master/stanfordCars.ipynb as the structure. The MaskRCNN https://github.com/matterport/Mask_RCNN was used to generate segmented car. In the dataset, there are the original cropped image and the segmented one (with white background). Train - valid dataset split: 80%. You can see the training process in stanfordCars_AWS.ipynb file. 

For prediction, 
- Please install the fastai library (https://github.com/fastai/fastai/blob/master/README.md#installation). or by conda install -c pytorch -c fastai fastai
- Download the trained model (stanford-cars-mixed_v.pth in [https://drive.google.com/open?id=1zI8djkX6PqKynLFSY4cVYYjiiOy246uj]). 
- Create folder tmp in stanford_cars folder.
- Create a 'test' folder (extract or put your test data here) and a 'models' folder under tmp.
- Put the stanford-cars-mixed_v.pth in ./tmp/models/
- Then run the jupyter notebook stanfordCars_AWS_prediction.ipynb file. It will guide you to infer single file or by folder.

Weakness:
- Because MaskRCNN prediction is not perfect, the segmented prediction can be wrong or 
- It cannot catch any of the car in the image or
- It segment the unwanted car.

Notes:
- I try segmenting the testdata but the accuracy was worse. There won't be segmented test data.

### With cropped train data + segmented train data (MaskRCNN)
Overall accuracy: 77.07 % (on cars_test data)

Next steps:
- Try not cropping, then segment the dataset. Mix it with original image.

### With cropped train data +original data+ cropped segmented data + resized segmented train data (MaskRCNN)
Overall accuracy: 85.11 % (on cars_test data)

Take-away points:
- Cropping and segmenting dataset can't improve the accuracy from baseline (mazenmel repo).
- Unless the original image exists on the train dataest.

