# Operationalizing Machine Learning in Azure

*Overview*
This project is part of the Udacity Azure Machine Learning Nanodegree. The objective of this project is to configure a cloud-based machine learning production model, deploy it, consume it and create automated process creating, publishing and consuming a pipeline.

The dataset is data from a bank marketing campaign. The aim of the campaign was to increase the number of subscribers to the bank term deposit. In this project we will try to predict with a "yes" or a "no", whether a client will subscribe to the product or not.

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model". 

## Key Steps
Step 1: Authentication
As i am using Udacity lab this step was skipped.

Step 2: Automated ML Experiment
Firstly we need to create a dataset using the URI of our dataset
![task1screenshot1](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/27c84f2f-46f2-4f9a-bb4e-7c2ffd7981de)

We create a compute cluster with Standard D3v2 with a minimum number of nodes of 1.

We proceed creating an Automated ML Experiment
![task1screenshot2](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/08762253-30f1-4313-a8f6-fca6b3fc7eb6)

![task1screenshot3](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/de0ba2b8-4094-4f1b-b9df-033da784e242)

The best model was found:
![task1screenshot4](https://github.com/samfrost23/nd00333_AZMLND_C2/assets/99268262/ce796a90-c123-48bc-a533-4cee14a329a0)

Step 3: Deploy the Best Model
Here we fnd the best model and select Deploy, choosing to enable authentication and Azure Container Instance (ACI), below we can see the Deployed End Point

Step 4: Enable Application Insights
I enabled application insights on the deployed model by running logs.py which enables them

Step 5: Swagger Documentaton
We use Swagger to easily view document and consume RESTful web services wth API's in HTTP requests. To enable Swagger I ran serve.py and Swagger.sh with correct ports, loading localhost with the port we can then explore the model using the swagger.json which can be downloaded from the best deployed model.

Step 6: Consume Endponts
Using endpont.py I added the score_url & key, I was then able to run a sample test to consume the endpoint

Step 7: Create, Publish and Consume a Pipeline
I have a Jupyter Notebook which uses dataset, cluster, keys and model names and creates the pipeline and then publishes the pipeline using Python SDK

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:
