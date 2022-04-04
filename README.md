Hey there 👋,

This work is dedicated to building deep learning models for classifying between healthy bones, bones requiring medical attention and bones which are beyond repair. Hope you will like it!


---
## Deep Learning Model for Medical Imaging

<img width="600" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/problem_statement.jpg?raw=true">

---

## Depth into classes

The deep learning models are trained on specific categories of bones such as  hand, legs wrist etc to start with and there are multiple types of fractures accounted in fractured class and bones beyond repair class. This process can be scaled up based on requirements such as more categories of bones, more types of fractures, segregation within classes for further classification etc.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/depth_into_classes.jpg?raw=true">

---

## A bit more depth into fractured and bones beyond repair classes.

<img width="600" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/depth_into_classes_2.jpg">

---
## Data Collection

<img width="400" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/data_collection.jpg?raw=true">

---

## Optimal Image resize resolution for model training

For finding a starting value of optimal image resize resolution is shown. This step is necessary as the single image resizing value for all training images should not be too low or too high considering original resolution of input images for model training, for model to be able to capture features properly. 

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/optimal_resolution.jpg?raw=true">

---

## Image to Array and Store

After converting images to arrays, which are our input matrix for training model. We save the arrays in numpy compressed zips to consume them later directly as it reduces the loading times during model experimentation phase. 

<img width="600" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/image_arrays.jpg?raw=true">

---

## Workflow

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/workflow.jpg?raw=true">

---

## Data Look-up

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/data_look_up.jpg?raw=true">

---

## Data Augmentation: Initialization and Hyperparameters

There are various hyperparameters in data augmentation to work around with for improving model generalizing ability and some of the hyperparameters are commented in the image below i.e. they are not suitable for model training for our case study as for example introducing a shearing range as hyperparamter may confuse the model with a fractured class and bones beyond repair class as the later class is also based on the degree of fracture condition in bone and hence it would cause model to train on ambigious images. Hence the commented hyperparameters are preferred not to be used for our particular use case.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/data_augmentation.jpg?raw=true">

---

## Model metrics Initialization and Hyperparameters

The model was initially started training on 2 classes i.e. healthy and fractured class as the data was explicitly not available online for training. Later after using Bing API to gather image data for 3rd class i.e. bones beyond repair, the problem statement was translated to three classes image classification with minor changes in the code  

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/model_parameters.jpg?raw=true">

---

## Model Building Workflow

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/model_building_workflow.jpg?raw=true">

---

## Model Version 1

Model Version 1 is the priliminary model built using 2 classes i.e. healthy and fractured bones at start for which we had dataset initially. The custom model stats are shown in the image.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/model_v1.jpg?raw=true">

---

## Model Version 2

Model Version 2 is built with a better custom model architecture than model version 1. This model base architecture focusses on capturing large features in the beginning using larger filter/kernel sizes and then learning on finer and complex features on subsequent layers by reducing the filter size and increasing the number of filters unlike model version 1 where there was a constant feature learning from subsequent layers.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/model_v2.jpg?raw=true">

---

## Model Version 2 and its variations

Model Version 2 is selected as base for further experimentation and the modifications applied for different experiments are such as changing recommended optmizers for this use case for comparing accuracies, reducing the number of neurons in subsequent dense layers for finding accuracies at cheaper networks and comparing base model having 3 channels (RGB) with base model having single channel (greyscale) as this is a case of x-ray images.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/model_v2_variations.jpg?raw=true">

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/model_v2_variations_2.jpg?raw=true">

---
