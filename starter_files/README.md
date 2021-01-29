## Bank Marketing Predictor: Training, Deploying and Consuming the ML model

This project is part of the Udacity Azure ML Nanodegree. In this project, we focus on 3 main steps:
  1. Creating a pipeline and training a Machine Learning model using AutoML.
  2. Publishing the pipeline and deploying the trained ML model using the Python SDK and the ML Studio.
  3. Consuning the deployed model by sending sample JSON data using Python SDK.

## Architectural Diagram
![architecture-diagram](./screenshots/architecture.png)

As visible in the above architecture, we can access Azure ML either from the az command line interface (CLI) or through the Azure ML Studio. Before we begin training an ML model, its important to fetch the dataset and register it into Azure Datastore for future use. This data is then preprocessed to convert it into a form suitable for training an ML model. After this, we create a new experiment and schedule the model training run on a compute cluster. After the model is trained, it is then deployed on the Azure Container Instance (ACI) and an endpoint is provided with which various external services can interact. We can automate the entire end-to-end model training and deployment process by creating and publishing a Pipeline. Once a pipeline is published, an endpoint is provided using which various external services can kick-off the pipeline run as and when required.


## Key Steps
1. We start off by uploading and registering the Bank Marketing dataset in the Azure Datastore. The same can be observed in the screenshot below.

![datastore-overview](./screenshots/p2-RegisteredDataset.PNG)

![datastore](./screenshots/p2-BMDataset.PNG)

2. After the dataset is registered, we create an AutoML run and add the above dataset as an input data on which the models train. After about 30 minutes, the AutoML run completes with Voting Ensemble as the best performing model. The same can be observed in the screenshot below.

![automl-run-overview](./screenshots/p2-AutoMLRunCompleted.PNG)

3. We then analyze the performance of the model by looking at its metrics as shown below.

![automl-run-overview](./screenshots/p2-AutoMLBestModel.PNG)

4.

## Screen Recording
The screencast of the project is available at the following URL: https://youtu.be/5Pi0KHkiBSo

The points covered in the screencast are:
  1. Working deployed ML model endpoint.
  2. Deployed Pipeline
  3. Available AutoML Model
  4. Successful API requests to the endpoint with a JSON payload
