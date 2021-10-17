# Training Mask R-CNN for taxi detection

## How I created the dataset
**Taxi dataset**  
Where to get the dataset : https://storage.googleapis.com/openimages/web/index.html  

Tools to get the dataset : follow the README.md in https://github.com/theAIGuysCode/OIDv4_ToolKit  

Or you can follow my steps in your terminal:
- create virtual environment `$python -m venv oid_download`
- activate the virtual environment `$source venv oid_download/bin/activate`
- clone or download the repository `$git clone https://github.com/EscVM/OIDv4_ToolKit.git`
- cd into the repository folder `$cd OIDv4_ToolKit`  
- install required packages `$pip install -r requirements.txt`  
- download train set `$python main.py downloader --classes Taxi --type_csv train`  
- download validation set `$python main.py downloader --classes Taxi --type_csv validation`
- download test set `$python main.py downloader --classes Taxi --type_csv test`

The downloaded dataset will be stored in `OIDv4_TookKit/OID/Dataset/`  

The downloaded dataset comprises of images and their annotation txt files (in folder 'Label')  

## How to train the Mask R-CNN
**training_MaskRCNN_for_taxi_detection.ipynb**  
In this notebook, I train the Mask R-CNN model on one class dataset which is Taxi datset.  

First, I create a model, load pre-trained weights except for the output layers.  

Then, I create dataset for Mask R-CNN model, and train the model.  

After that, I test that my model is functional by testing it on an image.  

Finally, the mean average precision (mAP) of the model are calculated in evaluation step.  
