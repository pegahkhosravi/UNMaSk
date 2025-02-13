# Understanding Data preparation from Whole slide images (WSI)

Digitalization of histopathology slides allows the use of powerful deep learning algorithm integration and it is further explored and used as a tool to aid the diagnostic process to make a more precise assessments. To achieve them we need tools that can support data preparation systematically. Our tool supports the annotation extraction from WSI without much dependence on the whether annotation is done on a WSI or on a tile level. Currently our tool supports annotations performed in both Aperio and Hamamatsu images. Recently there is significant interests, highlighting the need for creating powerful database for morphological tissue structures to study its association with its surrounding microenvironment for tissue types such as breast, lung and prostate. One such article is cited in the reference section below.

In this section we will summarize how we parse the freehand annotations drawn on WSI to train DCIS segmentation model.

For our demonstration, we have used Imagescope which is a generic open source tool, available for performing annotation on WSI images.

It is important to know how to extract the regions and the vertices that form these free-hand annotations. Once we are comfortable
extracting them we could export to any co-ordinate system and can be parsed to the training algorithms.

For demo purpose, I have used a CMU-1.ndpi downloaded from the following web link (http://openslide.cs.cmu.edu/download/openslide-testdata/Hamamatsu/)
 
Note: In general WSI images are high in memory. Corresponding authors of the publication can be contacted to see if the WSI can be made available (PLN,YY,ESH). Please  the Data availability section of the manuscript to find out more.
 

1. Visualization

<p align="center">
  <img src="training_material/cmu-1_ndpi.png" width="800"/>
  <img src="training_material/T3_svs.png" width="800"/>
</p>

 
                            
Square raw directory contains the whole slide images and the respective annotations.
Square annotation directory contains 
    1. positive example saved in Mat_files/pos directory
    2. negative example saved in Mat_files
    3. Gt.im is the original cws patch and GT.Mask contains the manual segmentation mask.
	

Summary
1. Read whole slide image (Image format supported by imagescope and openslide  is used here for the purpose of explaination).
2. Extract the free hand vertices.
3. Save the binary mask for processing.
4. Annotation supporting two whole slide image formats are provided here.

## Visualisation of randomly sampled images with free hand annotations on tiled images  
<p align="center">
  <img src="training_material/DCIS_freehand_sampled_pos_img_movie_001.gif" width="250" height="250"/>
  <img src="training_material/DCIS_freehand_sampled_pos_mask_movie_001.gif" width="250" height="250"/>
  <img src="training_material/DCIS_freehand_sampled_pos_overlay_movie_001.gif" width="250" height="250"/>
</p>

# Reference
Lindman, K., Rose, J.F., Lindvall, M., Lundström, C. and Treanor, D., 2019. Annotations, ontologies, and whole slide images–Development of an annotated ontology-driven whole slide image  of normal and abnormal human tissue. Journal of Pathology Informatics, 10.
