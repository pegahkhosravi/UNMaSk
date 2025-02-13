## UNMaSk: Unmasking the immune microecology of ductal carcinoma in situ with deep learning.

# Tissue segmentation module tree

 * [IHC Tissue Segmentation](./IHC_tissue_seg)
 * [TestImages](./TestImages)
    
 * [Train_IHC](./Train_IHC)
    * [imgs_train.npy](./dir1/imgs_train.npy)
    * [imgs_mask_train.npy](./dir1/imgs_mask_train.npy)
    * [imgs_mask_valid.npy](./dir/imgs_mask_valid.npy)
    * [imgs_valid.npy](./dir1/imgs_valid.npy)
 * [scripts](./scripts)
   * [predict_IHC_Inception_unet.py](./dir2/predict_IHC_Inception_unet.py)
   * [predict_parser.py](./dir2/predict_parser.py)
   * [slidingpatches.py](./dir2/slidingpatches.py)
   * [train_IHC_BLInception_unet.py](./dir2/train_IHC_BLInception_unet.py)
 * [model](./model_HE_Inception_unet)
    * [model-tissue-seg.h5](./dir2/model-tissue-seg.h5)    
 * [main.py](./main.py)
 * [requirements.txt](./requirement.txt)
 * [Dockerfile](./Dockerfile)
 * [README.md](./README.md)


### Parameters of train and predict for tissue segmentation pipeline

Command line arguments for Training

``` main.py --batch_size=4 --epochs=100 --mode=train```

Command line arguments for Prediction

` main.py --model=model_IHC_Inception_unet --test=TestImages --result=output `

--mode=WSI_test---> To directly run prediction on WSI image
For main_WSI.py
command line arguments example


` main_WSI.py --model=model_IHC_Inception_unet --test=WSI --result=output --mode=WSI_test`

Running tissue segmentation
usage: main.py [-h] [-model MODEL] [-test TEST] [-result RESULT] [-mode MODE]
               [-bs BATCH_SIZE] [-epochs EPOCHS]

optional arguments:

  `-h, --help                          show this help message and exit`
  
  `-model MODEL, --model MODEL         path to the model`
                        
  `-test TEST, --test TEST             path to test images`
                        
  `-result RESULT, --result RESULT     path to predicted result images`
                        
  `-mode MODE, --mode MODE             train or predict To perform prediction on test images prediction mode called by setting mode flag to test`
                        
  `-bs BATCH_SIZE, --batch_size BATCH_SIZE    batch size of training images`
                        
  `-epochs EPOCHS, --epochs EPOCHS            total number of epochs`


### Docker Container

```docker://nrypri001docker/tf:tsv1 ```

### Publicly accessible weblink

https://hub.docker.com/repository/docker/nrypri001docker/tf

# Citation

# Reference

All training data of carcinoma in situ regions that were annotated as a part of the project is made available in this github repository.
Training data tiles were anonymised from raw HE image tiles. Request for data access for the Duke samples can be submitted to E.S.H and Y.Y

# Training
Data preparation and implementation codes are maintained in this repository and will be periodically updated. Please contact the corresponding authours for future colloborations and any queries regarding the implementation.

