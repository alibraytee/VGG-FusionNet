# **VGG-FusionNet: A Feature Fusion Framework from CT scan and Chest X-ray Images based Deep Learning for COVID-19 Detection**

In this project, we propose a novel deep learning framework called "[*VGG-FusionNet*](https://ieeexplore.ieee.org/abstract/document/10031251)", which accurately detects the coronavirus by integrating features from both CT scan and CXR images. Our approach involves extracting features from these images using convolutional layers from GoogLeNet, ResNet, and VGG, and then fusing them prior to training through fully connected layers. Our results show that the use of VGG's convolutional layers achieved the best overall performance, with an accuracy of 0.93


## Conference

*2022 IEEE International Conference on Data Mining Workshops (ICDMW)*

## Authors

Yihan Zhou; Jiali Liu; Zekun Yang; Tianyi Liu; Xinyue Meng; Zhuocheng Zhou; Ali Anaissi; **Ali Braytee**

## Data
Public data must be downloaded from (https://drive.google.com/drive/folders/1VYYw-xPGgs2s6JkL3wlmW6Jgn11S0afi?usp=share_link)

**The datasets consist of 3 parts (organized in 3 folders):**

1. The sampled dataset was used for training and testing and would be split into a train set and a test set. The evaluation performed on the test set is called internal evaluation.

There are four files total in this subfolder:
The input file loaded using np.load from npz file is similar to a dictionary, and we can use keys to visit values.
 - CT_imagel.npz stores 1 group of arrays of CT images (224*224), and needs to be read in with “np.load” and extracted with the key[‘arr’].
 - CT_label.csv stores demographic information and labels of CT images. Demographic information includes age, gender, and country. The column finding is the label column containing COVID-19, Normal, and Pneumonia.
  - CXR_imagel.npz stores 1 group of arrays of CXR images (224*224), and needs to be read in with “np.load” and extracted with the key [‘arr’].
   - CXR_label.csv stores demographic information and labels of CXR images. Demographic information includes age, sex, and  location. Please note location here refers to the same column country
   in the CT_label.csv. The column finding is the label column containing COVID-19, Normal, and Pneumonia.
2. The external dataset has different data sources than the sampled dataset and was used to test the generalizability of our models externally, for which we called it external evaluation. The dataset only consists of 1 file ExternalData.npz. It has 3 groups of arrays. Key [‘arr1’] extracts np arrays of the CT images and key [‘arr2’] extracts np arrays of the CXR images for external evaluation, while key [‘arr3’] extracts the label information of all the images

3. The iran and china dataset consists of 2 countries' image data and was used for comparison experiments to  train and test our final model on different countries. The load-in data from file Two_country_data.npz has 6 groups of arrays. For China’s dataset, key [‘arr1’] extracts np arrays of China CT images, key [‘arr2’] extracts np arrays of China CXR images, and key [‘arr3’] extracts the label information of China CT and CXR images. For Iran’s dataset, key [‘arr4’] extracts np arrays of Iran CT images, key [‘arr5’] extracts np arrays of Iran CXR images, and  key [‘arr6’] extracts the label information of Iran CT and CXR images

##Code
The code files are numbered as our approximate experiment sequence.
1. Data files used in the files are stored locally in our Google Drive. If you would like to download the data files yourself, you could go to the Data folder.
2. experiments_VGG_fusion.ipynb contains experiments on fusion weight, self-defined MLP with VGG fusion, and testing CT and CXR individually on our VGG fusion model.

## Citation

Zhou, Y., Liu, J., Yang, Z., Liu, T., Meng, X., Zhou, Z., ... & Braytee, A. (2022, November). VGG-FusionNet: A Feature Fusion Framework from CT scan and Chest X-ray Images based Deep Learning for COVID-19 Detection. In 2022 IEEE International Conference on Data Mining Workshops (ICDMW) (pp. 1-9). IEEE.
