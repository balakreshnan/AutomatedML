# Automated Machine learning End to End Hack

## Citizen Data science open hack

## Introduction

Automated Machine Learning hackathon: To learn how to use automated machine learning build models and deploy to production.

## Agenda

- Introduction to Openhack
- Introduction to Azure Machine learning - 1 hour
- Introduction to Machine learning Ops  - 1 hour
- Openhack use case introduction - 4 hours
- Deploy model - 1 hour
- Clean up - 15 minutes
- Recap - 1 hour

## Use Case

- Predicting population growth for years to come. Prediciting population provides economist to know how to build the next generation supply chain across the world.
- This information also allows countries and state to plan their future for healthcare, consumer demand and even urban development.
- Build a end to end pipeline
- Move data from source into Azure using Azure data factory
- Process data as you move into Azure storage
- We can use data flow in Data factory to process data to consume in machine learning
- ETL/Data Engineering is the scope of data processing
- There is no need to format data for ML algorithmns
- Tabular data is enough
- Make sure all the features and label are available
- To Showcase Data Ops + Ml Ops
- End to end process to get the data and process and then create machine learning models and consume
- Note: the accuracy of the model is not important
- We are using regression as a sample to predict population
- Assumption is the source data in Azure Open data set and validate the configuration

## Architecture

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/automlarch.jpg "Architecture")

## Azure Resources

- Azure Account
- Create a Resource group called automlopenhack
- Create Azure Storage account called automloutput
- Create a Azure Data Factory - automladfopenhack
- Azure open data set configuration
- Create Azure machine learning service
- Also create a container registry to store model pickle files
- Create a compute-cluster
- Create a Inference-cluster for AKS
- List of resources created

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner44.jpg "Architecture")

## Steps

- Create Data factory copy pipeline
- Create a blob storage
- For URI : https://azureopendatastorage.blob.core.windows.net/
- for SAS key: sv=2019-02-02&ss=bfqt&srt=sco&sp=rlcup&se=2025-04-14T00:21:16Z&st=2020-04-13T16:21:16Z&spr=https&sig=JgwLYbdGruHxRYTpr5dxfJqobKbhGap8WUtKFadcivQ%3D

- Create a blob source
- save the input as azureopendataste

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner0.jpg "Architecture")

- Select the Source

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner1.jpg "Architecture")

- Choose the container
- Choose censusdatacontainer

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner3.jpg "Architecture")

- Click next to view the schema

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner4.jpg "Architecture")

- Next create ADLS gen2 as destination

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner5.jpg "Architecture")

- Name it as ADLSoutput
- Select the subscription and storage account name

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner6.jpg "Architecture")

- Choose a container

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner7.jpg "Architecture")

- Click Next and Next
- Keep everything as default
- Click Finish

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner8.jpg "Architecture")

- Wait the deployment to run

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner10.jpg "Architecture")

- View the transfer

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner9.jpg "Architecture")

## Now to Azure Machine learning setps

- Lets create a setup
- First Create a dataset and datastore

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner11.jpg "Architecture")

- create a datastore

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner12.jpg "Architecture")

- Select the folder

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner13.jpg "Architecture")

- View the file and select first column as header

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner14.jpg "Architecture")

- Validate the column

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner15.jpg "Architecture")

- Click next and click Create

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner16.jpg "Architecture")

- Create Automated ML experiment

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner17.jpg "Architecture")

- Select the dataset

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner18.jpg "Architecture")

- Create a compute cpu-compute
- Use 0 to 2 nodes is good

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner19.jpg "Architecture")

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner20.jpg "Architecture")

- Select the regression

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner21.jpg "Architecture")

- Click finish
- Click Run

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner22.jpg "Architecture")

- Running

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner23.jpg "Architecture")

- Once the experiment completed
- usually takes 2 to 3 hours

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner24.jpg "Architecture")

- Go to experiment and view the output

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner25.jpg "Architecture")

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner26.jpg "Architecture")

- Go to Metrics and view

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner27.jpg "Architecture")

- Only the best model will have view explanation

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner28.jpg "Architecture")

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner29.jpg "Architecture")

- Check the explanation or feature importance to see which columns had the most impact on prediction
- Logs model information

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner30.jpg "Architecture")

- Those are the columns we need to use
- Select the best model and Deploy
- Deploy to AKS cluster
- Create AKS cluster
- Go to Compute and create inference cluster

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner31.jpg "Architecture")

- Select Vm configuration
- I am choosing Dev/Test since this is for hackathon
- For production note minimum 12 nodes AKS cluster has to be created for HA
- Production config below

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner32.jpg "Architecture")

- Dev/Test configu

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner33.jpg "Architecture")

- Then click create
- AKS cluster creation started

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner34.jpg "Architecture")

- Wait for the cluster to start

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner35.jpg "Architecture")

- Then go back to experiment and Deploy process

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner36.jpg "Architecture")

- Wait for REST API deploying is complete

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner37.jpg "Architecture")

- Once completed the API should have been deployed

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner38.jpg "Architecture")

- Click aksdeploy left to succeeded to go to Endpoint information
- Once created an Endpoint will be created

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner39.jpg "Architecture")

- Click Test tab
- Type in the following information

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner40.jpg "Architecture")

- Click Test and see the output

```
decennialTime : 2020
zipCode: 77480
race: WHITE ALONE
sex: Female
minAge: 56
maxAge: 59
```

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner41.jpg "Architecture")

- Click Endpoint and should see the model endpoint deploy

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner42.jpg "Architecture")

- Display Models

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner43.jpg "Architecture")

## Cleanup

- Delete all the resources
- Drop the entire Resource group to get rid of all the components


## Resource Deploy

- I have downloaded the Resource manager template and stored in zip to recreate environment in power shell

## Comments and Feedback

## Conclusion

- This is a beginner Automated Machine learning hack. Intermidate and Expert level will be next