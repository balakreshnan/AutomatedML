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