# Automated Machine learning End to End Hack

## Use Case

- Build a end to end pipeline
- Move data from source into Azure using Azure data factory
- Process data as you move into Azure storage
- We can use data flow in Data factory to process data to consume in machine learning
- ETL/Data Engineering is the scope of data processing
- There is no need to format data for ML algorithmns
- Tabular data is enough
- Make sure all the features and label are available

## Architecture

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/images/automlarch.jpg "Architecture")

## Azure Resources

- Azure Account
- Create a Resource group called automlopenhack
- Create Azure Storage account called automloutput
- Create a Azure Data Factory - automladfopenhack
- Azure open data set configuration

```
# storage account details
azure_storage_account_name = "azureopendatastorage"
azure_storage_sas_token = "sv=2019-02-02&ss=bfqt&srt=sco&sp=rlcup&se=2025-04-14T00:21:16Z&st=2020-04-13T16:21:16Z&spr=https&sig=JgwLYbdGruHxRYTpr5dxfJqobKbhGap8WUtKFadcivQ%3D"
```

## Steps

- Create Data factory copy pipeline
- Create a blob storage
- For URI : https://azureopendatastorage.blob.core.windows.net/
- for SAS key: sv=2019-02-02&ss=bfqt&srt=sco&sp=rlcup&se=2025-04-14T00:21:16Z&st=2020-04-13T16:21:16Z&spr=https&sig=JgwLYbdGruHxRYTpr5dxfJqobKbhGap8WUtKFadcivQ%3D

- Create a blob source
- save the input as azureopendataste

![alt text](https://github.com/balakreshnan/AutomatedML/blob/main/Beginner/images/beginner1.jpg "Architecture")

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