---
title: 'Google ML Certificates Series- Google Cloud Big Data and Machine Learning Fundamentals-2'
date: 2023-02-10
permalink: /posts/2023/blog-post-5/
tags:
  - Google
  - Certificate

categories:
  - Machine Learning 
  - Study
---

# Machine Learning Options on Google Cloud

Google provides a total of 4 options for executing ML
* BigQuery ML: Use SQL queries
* Pre-built APIs: ML models pre-built by google 
* AutoML: Build ML models in Vertex AI
* Custom Training: Code own ML environment

<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-1.png" style="max-width: 70%;">
</p>


## Prebuilt-APIs
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-2.png" style="max-width: 70%;">
</p>

## AutoML
Two techniques are critical: Transfer Learning and Neural Architecture Search 

### Transfer Learning
Transfer learning is a powerful technique that lets people with smaller datasets, or less computational power, achieve state-of-the-art results by taking advantage of pre-trained models that have been trained on similar, larger data sets.

<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-3.png" style="max-width: 70%;">
</p>
### Neural Architecture search
AutoML is powered by the latest machine-learning research, so although a model performs training, the AutoML platform actually trains and evaluates multiple models and compares them to each other. This neural architecture search produces an ensemble of ML models and chooses the best one.
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-4.png" style="max-width: 70%;">
</p>
Transfer Learning

### How AutoML Works?
AutoML supports four types of data: image, tabular, text, and video
For each type of data AutoML solves different type of problems (a.k.a <mark style="background: #BBFABBA6;">objectives</mark>)

The ML Process:
1. Upload data
2. Inform ML of the problems to be solved 

Prebuilt API vs. AutoML
Pre-built API: use pre-built ML models
AutoML: uses custom-built ML models

## Custom Training
To custom code in google platform we use Vertex AI Workbench. 
Before starting the coding you have to choose the environment in which the code will run. 

> Options for environment: Pre-built container, Custom container
> Pre-built container a kitchen with pre-defined Dependencies and Libraries <p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-5.png" style="max-width: 70%;">
</p>

### Vertex AI
Its a unified platform: have one digital experience to create, deploy and manage models over time and at scale.

## Google Cloud AI portfolio
It can be visualized into three layers
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-6.png" style="max-width: 70%;">
</p>

---
# The Machine Learning Workflow with Vertex AI

The coding process in machine learning is also called `programming`; however, this is somewhat different from traditional programming. 

The characteristics of <mark style="background: #BBFABBA6;">traditional programming</mark> are: 
* (data)+1(rule)=2(answers)
* can only follow algorithms that have been set up

Unlike traditional programming, in machine learning programming, you feed a big amount of data and select the ML model to let the PC get the answer for you. For this you require lots of storage and Fast calculation capacity hence here comes in Cloud Storage and Cloud computing.
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-7.png" style="max-width: 70%;">
</p>

## Key processes in ML
#### What is ML? AI? 
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-8.png" style="max-width: 70%;">
</p>
#### Supervised Learning Vs. Unsupervised Learning
Supervised Learning: Every data must have a label 
Un supervised Learning: Does not require a label
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-9.png" style="max-width: 70%;">
</p>
#### ML process
There are three key processes in ML: data preparation, model training, and model serving. **(This process is not linear)**
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-10.png" style="max-width: 70%;">
</p>

### Data preparation (Selection, Preprocessing, Transformation)
Data preparation involves two steps: Data Uploading and Feature Engineering 
As seen before an engineer handles different types of data during this process. 
The two categories is in terms of frequency and structure type
> ❗ remember 
> In terms of frequency: Streaming vs. batch data 
> In terms of structure: Structure vs. Unstructured data

The data preparation process starts with the uploading of the data. 
> remember Vertex AI accepts 4 types of data: image, tabular, text, video

The next step is feature engineering. select and process the data. A `feature`  refers to a factor that contributes to the prediction (like independent variable or a column). Vertex AI have built in Feature Store to enable this activity. 

### Model training (Mining)
The model training happens in various iterations of training and evaluation.
While AutoML and Pre-built APIs does the job for you (you are only required to let the program know what task you want to do) BigQuery ML and Custom Training requires the selection of hyperparameters (learning rate, batch number, epoch, etc...)
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-11.png" style="max-width: 70%;">
</p>
#### Model Evaluation
Most common evaluation metrics: Confusion Matrix and Feature Importance. 

##### What is a Confusion matrix?
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-12.png" style="max-width: 70%;">
</p>

|Recall|Precision|
|----- | ------|
|$$\text{Recall} = \frac{TP}{TP+FN}$$ | $$\text{Precision} = \frac{TP}{TP+FP}$$|

#### Feature importance
Represented in a Barchart


### Model Serving 
This step refers to the deployment, monitoring, and management of the developed ML model

#### Model deployment and monitoring
Model Deployment
Three options to deploy the model.
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-13.png" style="max-width: 70%;">
</p>
Model Monitoring: It automates, monitors, and governs machine-learning systems by orchestrating the workflow in a serverless manner.
<p align = "left">
  <img src = "https://raw.githubusercontent.com/elias-lee/lelias.github.io/master/_posts/resources/ml_certi_resource/course1_week2-14.png" style="max-width: 70%;">
</p>