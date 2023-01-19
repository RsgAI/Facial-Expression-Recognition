
---
# *<center>Deep Learning Based Facial Expression Recognition</center>*

*This project is an observational preliminary study for the training of the facial expression recognition model, which is one of the components of the 
[**Computer Vision and Deep Learning Based Virtual Teacher**](https://github.com/RsgAI/Computer-Vision-and-Deep-Learning-Based-Virtual-Teacher "GitHub Repository") project.
In this project, deep learning-based facial expression recognition will be implemented on the
[**Expression in-the-Wild(ExpW)**](http://mmlab.ie.cuhk.edu.hk/projects/socialrelation/index.html "Official Website") dataset.
Comparisons will be made between models and samples by training different models with different quality and quantity samples of the relevant dataset.*

### Note: Work on this project is being continued
---

### *Dataset*
*In this context,
[**Data**](https://drive.google.com/drive/folders/1SDcI273EPKzzZCPSfYQs4alqjL01Kybq "Google Drive Link")
of the 
[**Expression in-the-Wild(ExpW)**](http://mmlab.ie.cuhk.edu.hk/projects/socialrelation/index.html "Official Website") dataset will be used.
Also see [**ResearchGate Link**](https://www.researchgate.net/figure/Example-images-of-the-proposed-ExpW-dataset_fig1_308409718 "ResearchGate Link") of dataset.*

---

### *Version*

- _Python Version: **3.9.12**_
- _Numpy Version: **1.22.3**_
- _OpenCV(cv2) Version: **4.5.1**_
- _Pandas Version: **1.4.3**_
- _Matplotlib Version: **3.5.2**_

---

# *<center>Notebooks</center>*

---

## *Data Preparation*

### - Preparation

1. **Preparation1:** First Step of data preparation process.
In this notebook file, dataset was statistically analyzed and checked manually.
The images with the highest and lowest FaceBoxConfidence values were read with the _**opencv**_ library and examined manually.
The balance of some samples in the dataset was examined by drawing charts.
See <ins>_/DataPreparation/Preparation1.ipynb_</ins> file for details.
2. **Preparation2:** Second Data Preparation Process.
In this notebook file Data with FaceBoxConfidence value above 70 was selected as a sample.
The images in the sample was read with the _**opencv**_ library and the related faces were resized as (224, 224).
The reason why images were resized this way will be explained in the Training section.
Sample was splitted into Training, Validation and Test data.
Sample images were drawn from Training Validation and Test data.
Reorganized data was saved as pkl files with the name Sample1 for future use.
See <ins>_/DataPreparation/Preparation2.ipynb_</ins> file for details.
3. **Preparation3:** Third Data Preparation Process.
In this notebook file a perfectly balanced sample was selected.
The images in the sample was read with the _**opencv**_ library and the related faces were resized as (224, 224).
The reason why images were resized this way will be explained in the Training section.
Sample was splitted into Training, Validation and Test data.
Sample images were drawn from Training Validation and Test data.
Reorganized data was saved as pkl files with the name Sample2 for future use.
See <ins>_/DataPreparation/Preparation3.ipynb_</ins> file for details.
4. **Preparation4:** Fourth Data Preparation Process.
In this notebook file a sample that can be considered balanced at a certain level was selected.
The images in the sample was read with the _**opencv**_ library and the related faces were resized as (224, 224).
The reason why images were resized this way will be explained in the Training section.
Sample was splitted into Training, Validation and Test data.
Sample images were drawn from Training Validation and Test data.
Reorganized data was saved as pkl files with the name Sample3 for future use.
See <ins>_/DataPreparation/Preparation4.ipynb_</ins> file for details.


---

## *Training*

*In this section, different models will be trained with the prepared samples and the results will be shown.
The models to be trained will be based on the architectures of the [**VGG16**](https://keras.io/api/applications/vgg/ "keras") and [**MobileNet**](https://keras.io/api/applications/mobilenet/#mobilenet-function "keras") pre-trained models.
See also [**MobileNet (GitHub)**](https://github.com/tensorflow/models/blob/master/research/slim/nets/mobilenet_v1.md "github") and [**Depthwise Separable Convolutions**](https://towardsdatascience.com/understanding-depthwise-separable-convolutions-and-the-efficiency-of-mobilenets-6de3d6b62503 "towardsdatascience").
See also [**VGG16 (TensorFlow)**](https://www.tensorflow.org/api_docs/python/tf/keras/applications/vgg16/VGG16 "tensorflow")*

*Many pre-trained models, including the ones to be used within the scope of this project, have been trained with (224, 224, 3) sized images containing pixel values in the [-1, 1] range.
This is why the images were resized as (224, 224, 3) in the Preparation section.
Also, for this reason, the pixel values will be converted to the range [-1, 1].
In this way, the data will be symmetrical and the performance of the [**Backpropagation**](https://en.wikipedia.org/wiki/Backpropagation "wikipedia") algorithm used during training will be increased.
See also [**This Question and Answer**](https://stackoverflow.com/questions/59540276/why-in-preprocessing-image-data-we-need-to-do-zero-centered-data "stackoverflow").
Therefore, training will be performed by converting pixel values to this range with the simplest method (pixel / 127.5 - 1).*

*The same trainings will be carried out by applying [**Data Augmentation**](https://en.wikipedia.org/wiki/Data_augmentation "wikipedia") to the data in order to observe the difference.
For details of the Data Augmentation process used in this application, see also [**Image Data Augmentation**](https://www.tensorflow.org/tutorials/images/data_augmentation "tensorflow").*

### - Sample1
1. **Training1:** First model training process. 
In this notebook file, a model based on VGG16 architecture were trained with the Sample1 sample.
Accuracy and Loss charts were drawn for the Training and Validation data, and the results obtained by evaluating the trained model with the Test data were printed.
Based on the Test data, prediction distribution charts were drawn for each label.
See <ins>_/Training/Sample1/Training01.ipynb_</ins> file for details.
2. **Training2:** Second model training process. 
In this notebook file, a model based on MobileNetV2 architecture were trained with the Sample1 sample.
Accuracy and Loss charts were drawn for the Training and Validation data, and the results obtained by evaluating the trained model with the Test data were printed.
Based on the Test data, prediction distribution charts were drawn for each label.
See <ins>_/Training/Sample1/Training02.ipynb_</ins> file for details.
3. **Training3:** Third model training process. 
In this notebook file, Data Augmentation operation were applied on Sample1 sample, a model based on VGG16 architecture were trained with this augmented data.
Accuracy and Loss charts were drawn for the Training and Validation data, and the results obtained by evaluating the trained model with the Test data were printed.
Based on the Test data, prediction distribution charts were drawn for each label.
See <ins>_/Training/Sample1/Training03.ipynb_</ins> file for details.
4. **Training4:** Fourth model training process. 
In this notebook file, Data Augmentation operation were applied on Sample1 sample, a model based on MobileNetV2 architecture were trained with this augmented data.
Accuracy and Loss charts were drawn for the Training and Validation data, and the results obtained by evaluating the trained model with the Test data were printed.
Based on the Test data, prediction distribution charts were drawn for each label.
See <ins>_/Training/Sample1/Training04.ipynb_</ins> file for details.

---


- _**Note:** All data files are deleted with their folders to save memory.
If notebook files are wanted to be run, images must be moved to <ins>/Data/RawData/Images/</ins> path and label.lst must be moved to <ins>/Data/RawData/Label/</ins> path in
[**Dataset**](https://drive.google.com/drive/folders/1SDcI273EPKzzZCPSfYQs4alqjL01Kybq "Google Drive Link")
Non-existent folders must be created and notebook files must be run in the specified order._

---

## <center>_I'd Be Glad If You Report Any Mistakes You Notice._</center>

---