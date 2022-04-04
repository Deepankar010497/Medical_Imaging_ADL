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
