<div class="clearfix" style="padding: 0px; padding-left: 100px; display: flex; flex-wrap: nowrap; justify-content: space-evenly; align-items:center">
<a href="http://bimcv.cipf.es/"><img src="https://github.com/BIMCV-CSUSP/BIMCV-COVID-19/blob/master/chestRx/logoinst.png?raw=true"</a><a href="http://ceib.san.gva.es"></a></div>

# Data Sources. [BIMCV-PadChest](http://ceib.bioinfo.cipf.es/covid19/padchest_neumonia.zip)
You can download the Raw images from this link --> http://ceib.bioinfo.cipf.es/covid19/padchest_neumonia.zip

You can download the resize images from  --> http://ceib.bioinfo.cipf.es/covid19/resized_padchest_neumo.tar.gz

You can download other resize images --> http://ceib.bioinfo.cipf.es/covid19/resized_padchest_neumo_32.tar.gz
# UPDATES

**Updates 27/03/2020**

Don't miss this news from MIT Tech. --> https://www.technologyreview.com/s/615399/coronavirus-neural-network-can-help-spot-covid-19-in-chest-x-ray-pneumonia/?utm_medium=tr_social&utm_campaign=site_visitor.unpaid.engagement&utm_source=Twitter#Echobox=1585319560

**New updates 26/03/2020**

Don't miss the next video from ESR --> https://www.youtube.com/watch?v=QFW8CmZ0cyM&feature=youtu.be

new data_augmentation_simplified.py from Roberto Paredes's contribution

**New updates 24/03/2020**

Following Roberto Paredes's suggestions we have resized the dataset 

**New updates 23/03/2020**

Following Roberto's suggestions we will leave a single partition, it will be easier.

**---**

## One example for helping to test
The tables that will be used to carry out the required model training are stored in one folder that contain the images. There are a total of 10 tables called "pneumo_dataset_balanced_x.tsv" where x takes values from 0 to 9. 
These files contain different partitions of the images and can be used individually or together if a "10-fold cross validation" is required. 

The most important data to take into account for the training phase are:

**Image ID:** name of the image file.

**StudyID:** study identifier.

**Patient ID:** patient identifier.

**Projection:** patient’s position when taking the radiography.

**Tags:** radiological findings found in the image.

**Group:** label of the class to which the image belongs. These labels can be:

* C - Control
* N - Pneumonia
* I - Infiltration
* NI - Pneumonia and infiltration

Partition: partition to which the image belongs. These values are:
* tr - Training
* dev - Development
* te - Test
## Run the code

To train the model example, you need to execute the following instruction:

python3 pneumo_cnn_classifier_training.py «FILE_TSV_BALANCED»


## RESULTS

### 4 classes {C,N,I,NI}

|  Participant | Model name  | Dev Accuracy | Test Accuracy  | Comments  |
|---|---|---|---|---|
| rparedes  | model1 | 67.97%  | ----  |  512x512 images, numpy |
|   |   |   |   |   |
|   |   |   |   |   |

### 2 classes C versus [I,NI,N]
|  Participant | Model name  | Dev Accuracy | Test Accuracy  | Comments  |
|---|---|---|---|---|
| jonandergomez  | model2 | 78.39%  | ----  |  512x512 images |
|   |   |   |   |   |
|   |   |   |   |   |

### 2 classes {C,N}
|  Participant | Model name  | Dev Accuracy | Test Accuracy  | Comments  |
|---|---|---|---|---|
| jonandergomez | model2 | 83.69% | 81.70% | 512x512 images, useless model because of overfitting, 98.89% of accuracy on training partition. Now trying to improve it. | 
| rparedes  | model2_rp | 84.06%  | ----  |  512x512 images, numpy |
|   |   |   |   |   |
|   |   |   |   |   |

