How to run the code ?

.....................................................................
.....................................................................
1. Instance Segmentation=Masking lesions on chest CT Scan images:

#Start with: 1_Instance_segmentation.ipynb colab ipython notebook.There are notes on colab for each part.
##To run the code first make sure all neccsary libraries are imported.
### If not !pip install <missing library>
#### Then check the last cell for config_dict
##### There you can find and configurate the model:
     Make sure that you have the needed directories and pretrained model with the .pth format in specifier directory
     The defualt is now : "segmentation_folder/pretrained_model_for_instance_segmentation/segmentation_model_both_classes.pth"
     Make sure to have some chest ct images in the directory which 
     The difault is now : segmentation_folder/images
     Make sure to have edited your notebook setting to GPU to speed-up the process 
###### Run the code and have the result masked chest CT Scan imgages with saved in the folder which by default is : segmentation_folder/results
####### GGO is masked with red color and C is masked with blue there are also probabality for each possibile lesion in bounding boxes
     

.......................................................................
.......................................................................
2. Training Classifier : 

# Start with 2.train_classifer.ipynb ipython notebook. There are notes for each part
## To run the code first make sure all neccsary libraries are imported
### If not !pip install <missing library>
#### Then check the last cell for config_dict
##### You already have some photos in train and validation directories which by default are:
        "train_data_dir": "Classification_folder/covid_data/cncb/train/
        "val_data_dir": "Classification_folder/covid_data/cncb/validation/
###### If you would like to train with other portion of images make sure they follow same formatting such as below        
       For example 0_something_somthing instead of Normal_something_something (more information on report)
       -- the following notes could be obviously done in main codes but i decided to do seperatly to avoid messing up with original code--
           You can use the code in label_map.py to rename the Kaggle covidx ct data set to map to standard name of the files
           You can use data splitter code to split train test validation
###### After preparing config_dict run the code but before that make sure you have edited notebook setting to GPU to speed up the process

........................................................................
........................................................................
3.Test_classifier

Now we have a model trained on our new data set
The new checkpoint is saved in classification_folder/checkpoints  from previous(train classifier) step
# To run the code first make sure all neccsary libraries are imported
## If not !pip install <missing library>
### Then check the last cell for config_dict
#### You already have some photos in test directory
#### If you would like to test other image:       
     For example 0_something_somthing instead of Normal_something_something
    you can use the code in label map python code to rename the kaggle covidx ct data set to map to standard name of the files
    you can use data splitter code to split train test val data
##### after preparing config_dict run the code but before that make sure you have edited notebook setting to gpu
      only point in this part is that you need to test the images with the checkpoint.pth file in saved models 
      (use the latest version of saved checkpoint)

####### you will see metrics and confusion matrix as out put

 ..............    DO NOT USE THIS CODE FOR SELF DIAGNOSING  ..........





    

