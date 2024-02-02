# Operationalizing Machine Learning in Azure

## Overview
This project is part of the Udacity Azure Machine Learning Nanodegree. The objective of this project is to configure a cloud-based machine learning production model, deploy it, consume it and create automated process creating, publishing and consuming a pipeline. I train a machine learning model using AutoML in Azure Machine Learning Studio and deploy the best model using Azure Container Instance and consume it using the REST endpoints. After this I also create and publish a pipeline using Python SDK.

The dataset is data from a bank marketing campaign. The aim of the campaign was to increase the number of subscribers to the bank term deposit. In this project we will try to predict with a "yes" or a "no", whether a client will subscribe to the product or not.


## Architectural Diagram

The Diagram below shows the steps followed implementing the project: 

![Untitled Diagram drawio](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/1e4c0167-64c4-4fa7-89a3-6a5a7e5a50d9)

## Key Steps
### Step 1: Authentication

As i am using Udacity lab this step was skipped.

### Step 2: Automated ML Experiment

Firstly I created a dataset using the URI of our dataset

![task1screenshot1](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/27c84f2f-46f2-4f9a-bb4e-7c2ffd7981de)

Created a compute cluster with Standard_D3_v2 with a minimum number of nodes of 1.

Then proceeded creating an Automated ML Experiment

![task7screen3](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/c66ea682-8277-424c-8bfe-1c17be119ff0)

Below we can see the completed run:

![task1screenshot2](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/08762253-30f1-4313-a8f6-fca6b3fc7eb6)

The listed models that ran:

![task1screenshot4](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/ce796a90-c123-48bc-a533-4cee14a329a0)


The best model:
![task1screenshot3](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/de0ba2b8-4094-4f1b-b9df-033da784e242)

### Step 3: Deploy the Best Model

Here I select the best model and select Deploy, choosing to enable authentication and Azure Container Instance (ACI), below we can see the Deployed End Point

![task2insights](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/9d07a50c-e979-4560-a325-739074d25377)

### Step 4: Enable Application Insights

I enabled application insights on the deployed model by running logs.py which enables them

![task2logsrunning](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/63af217d-e72f-4007-b6d0-666ff179b983)

![Screenshot 2024-02-01 150105](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/5b7d99d2-d260-48e8-92f1-d66bf2c90c9d)

### Step 5: Swagger Documentaton

We use Swagger to easily view document and consume RESTful web services wth API's in HTTP requests. To enable Swagger I ran serve.py and Swagger.sh with correct ports, loading localhost with the port we can then explore the model using the swagger.json which can be downloaded from the best deployed model.

![task5screenshot1](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/b7c4a686-c1ff-4c04-8e98-3d1436e48e70)

### Step 6: Consume Endponts
Using endpoint.py I added the score_url & key, I was then able to run a sample test to consume the endpoint

![task6screenshot1](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/ae48cbd1-6746-487d-bc0b-895d74be5128)

### Step 7: Create, Publish and Consume a Pipeline
I have a Jupyter Notebook which uses dataset, cluster, keys and model names and creates the pipeline and then publishes the pipeline using Python SDK

![Screenshot 2024-02-01 150144](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/799a7eb8-3556-4c78-a9bb-d83670be002c)

![Screenshot 2024-02-01 150203](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/77c1cc0e-2972-4a27-9e2a-0d13045323b7)

![task7screen12](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/08982785-244d-4469-8ced-c0725124d7e5)

![Bankmarketing dataset with the AutoML module pipeline](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/b4f151d8-a811-4ea2-b209-9c16473b195c)

![task7screen4](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/d06ef497-ef36-48e6-82e8-115010fce065)

We can view the pipeline run using the RunDetails widget:

![pipelinerunshow](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/7627bc28-1329-43ad-9d50-8aa08696a4fb)

## Screen Recording
Here is a screencast for the project 

https://drive.google.com/file/d/19IYyo2sowg5C1VTRY0mZFif7CAgS2T09/view?usp=sharing

## Future Work
Some ideas for improving the project in the future:

Increase the experiment timeout, this may improve the results as the AutoML can try to find more accuracy.

Enable Deep learning to possibly increase the performance
