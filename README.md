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

## Model Version 3

Model Version 3 is built with all three classes of the problem statement i.e. healthy, fractured and bones beyond repair class.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/model_v3.jpg?raw=true">

---

## Transfer Learning Model Version 1

With the help of custom models, the models could predict between the three classes with fair enough accuracies but for achieving highly accurate models there is a need for involving complex convolutional blocks and in mutiple layers. Creating such architecture and training them can be difficult if there are computational constraints, which is why transfer learning can be a great aid here where we can leverage these pre trained models for our own use case. Transfer Learning Model Version 1 is built using pre-trained model Inception v3 and the stats are shown in the image.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/transfer_learning_model_v1.jpg?raw=true">

---

## Transfer Learning Model Version 1 - Modification 1

The transfer learning model version 1 can become overconfident sometimes during prediction because of creating tight boundaries for classification during model training and hence to avoid this we can use regularizers to prevent model overfitting. This model is a variation of base model with addition of l2 regularization on each layers of the imported pre trained model.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/transfer_learning_model_v1_1.jpg?raw=true">

---

## Transfer Learning Model Version 1 - Modification 2

The transfer learning model version 1 Modification 1 happens to still show overfitting and hence to create some more non linearity and reduce down the number of features before making a decision on probablities for classifying bone classes, we add one dense layers followed by batch normalization and the results shows a reduction in overfitting nature of the model and knowledge from this experimentation can be further utilizated for generating higher accurate models.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/transfer_learning_model_v1_2.jpg?raw=true">

---

## Transfer Learning Model Version 2

The transfer learning model version 2 is built using pre-trained model Xception and results show a opportunity for further scope of impovements for highly accurate model with very less overfitting.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/transfer_learning_model_v2.jpg?raw=true">

---

## Transfer Learning Model Version 2 - Modification 1

The transfer learning model version 2 shows some overfitting and hence to create some more non linearity and reduce down the number of features before making a decision on probablities for classifying bone classes, we add one dense layers followed by batch normalization and the results shows a reduction in overfitting nature of the model and also an comparable increase in model accuracy and knowledge from this experimentation can be further utilizated for generating higher accurate models.

From all the models trained so far, this model shows the most favorable outcome. 

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/transfer_learning_model_v2_1.jpg?raw=true">

---

## Other Transfer Learning Models

Some other pre trained models have been tried upon and are not continued for further experiments based on the facts that they don't show promising results with the applied methods for use case. Future scope can include finding better methods to work around with these models for further comparision.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/other_t_l_models.jpg?raw=true">

---

## Model Demo Deployment

Transfer Learning model Inception V3 has been used as a use case for our problem statement for the sake of model deployment. As a part of standard practice, model deployment has been carried out using Azure Web App services using Azure pipelines for continous integration and creating docker images from github repository using azure container registry. Also the demo model deployment is carried out on Streamlit cloud services hosted from my Medical_Imaging_Deployment repository.

The link of the streamlit web app for the bone classifier model is given provided. 

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/model_deployment.jpg?raw=true">

Streamlit Web app link - [boneclassifier.com](https://share.streamlit.io/deepankar010497/medical_imaging_deployment/main/app.py)

---

## Model Details

Information and details about all the models are included in the notebooks in the github repository and can be refered as needed.

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/model_details.jpg?raw=true">

---

## Application and Future Work

<img width="700" align='center' src="https://github.com/Deepankar010497/Medical_Imaging_ADL/blob/main/Images/application_future_work.jpg?raw=true">


Thank you for your patience and hope you enjoyed reading my content!
