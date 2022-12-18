
---
# *<center>Deep Learning Based Facial Expression Recognition</center>*

*This project is an observational preliminary study for the training of the facial expression recognition model, which is one of the components of the 
[**Computer Vision and Deep Learning Based Virtual Teacher**](https://github.com/RsgAI/Computer-Vision-and-Deep-Learning-Based-Virtual-Teacher "GitHub Repository") project.
In this project, deep learning-based facial expression recognition will be implemented on the
[**Expression in-the-Wild(ExpW)**](http://mmlab.ie.cuhk.edu.hk/projects/socialrelation/index.html "Official Website") dataset.
Comparisons will be made between models and datasets by training different models with different quality and quantity parts of the relevant dataset.*

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

- _**Note:** All data files are deleted with their folders to save memory.
If notebook files are wanted to be run, images must be moved to <ins>/Data/RawData/Images/</ins> path and label.lst must be moved to <ins>/Data/RawData/Label/</ins> path in
[**Dataset**](https://drive.google.com/drive/folders/1SDcI273EPKzzZCPSfYQs4alqjL01Kybq "Google Drive Link")
Non-existent folders must be created and notebook files must be run in the specified order._

---

## <center>_I'd Be Glad If You Report Any Mistakes You Notice._</center>

---