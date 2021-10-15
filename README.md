# Object Detection with MaskRCNN

## How to make the object detection on an image
**object_detection_on_image.ipynb**  
Make object detection on the given image with Mask R-CNN model.  
And plot the image along with mask, bounding boxes, class id and confidence level.  

## How to train Mask R-CNN model on custom dataset
**Taxi dataset**  
Where to get the dataset : https://storage.googleapis.com/openimages/web/index.html  

Tools to get the dataset : follow the README.md in https://github.com/theAIGuysCode/OIDv4_ToolKit  

Or you can follow my steps :
- clone or download the repository `https://github.com/EscVM/OIDv4_ToolKit.git`
- cd into the repository folder `$cd OIDv4_ToolKit-master`  
- install required packages `$pip install -r requirements.txt`  
- download taxi dataset from OIDv6 `$python main.py downloader --classes Taxi --type_csv train`  

The downloaded dataset will be stored in `OID/Dataset/Train/Taxi`  

The downloaded dataset comprises of images and thir annotation txt files (in folder 'Label')  

I manage my dataset by separating images and annotation files into 2 folders named 'images' and 'annotations' respectively.  

Now, our data for creating Mask R-CNN dataset is ready.

**dataset_preparation.ipynb**  
Show the preparation process of creating Mask R-CNN dataset from the downloaded images and annotation txt files.  

Now, our Mask R-CNN dataset is ready to be used in training process.

**custom_train_Mask_RCNN.ipynb**  
In this notebook, I train the Mask R-CNN model on one class dataset which is Taxi datset.  

First, I create dataset for Mask R-CNN model.  

Then, I create a model, load pre-trained weights except for the output layers, and train the model.  

After that, I test that my model is functional by testing it on an image.  

Finally, the mean average precision (mAP) of the model are calculated in evaluation step.  
# training_MaskRCNN_for_taxi_detection
