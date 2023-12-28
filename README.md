# Tokyo Olympic Microsoft Azure


In this project, I utilized datasets related to the Tokyo Olympics and COVID-19, sourced from Kaggle and the ECDC website. I use Microsoft Azure services to create pipelines, manage storage, perform data transformations, utilize MySQL, and integrate with Power BI.

The main purpose of this project is to get familiar with the services of Microsoft Azure and how to use them in real-world scenarios. 

The task involves:
* Download datasets from Kaggle and ECDC website.
* Create an account on Microsoft Azure
* Create environments to use Azure's services.
* Use AzureDataFactory to create pipelines, link services, datasets, and triggers.
* Use AzureDataFactory's services called DataFlow for the transformation of the data. 
* Use AzureDatabricks for the transformation of the data.
* Use Snaypse Analytics for the transformation of the data.
* Use HD Insights for the transformation of the data.
* Use AzureMySQL and MicrosoftPowerBI for the creation of the dashboard. 

Tools that I used are:

![mysql](https://img.shields.io/badge/Kaggle-20BEFF.svg?style=for-the-badge&logo=kaggle&logoColor=white)
![microsoft Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=#0078D4)
![mysql](https://img.shields.io/badge/Databricks-FF3621.svg?style=for-the-badge&logo=databricks&logoColor=white)
![mysql](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)
![mysql](https://img.shields.io/badge/powerbi-F2C811.svg?style=for-the-badge&logo=powerbi&logoColor=white)




## Environment creation and Dashboard

First, I create a data lake storage account, blob storage, and datafactory environments, pin them in the dashboard name "Azure-Cloud-Project".


![Alt Text](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/dashboard.JPG)

I created the container name "sourcedata1" in blob storage and added the required dataset.


![Alt Text](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/blobstorage.JPG)


---
>You can download the dataset from Kaggle by writing the Tokyo Olympic Dataset
---

## Azure Data Pipelines
**1- Data Ingestion using Azure Blob Storage**

Firstly, I used Azure Blob Storage to copy data into Data Lake Gen2.

for the creation of the pipeline, I use Validation, Get Meta Data, If Condition, Copy, Delete, and Web activities.

![Capture3](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/Capture3%20Validationget%20meta%20data%20if%20activity.JPG)

![Capture3 with delete](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/Capture3%20with%20delete.JPG)



below is the screenshot of the successful run of the pipeline

![all running](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/all%20running%203.JPG)

I also used parameters, and variables to create a more generic pipeline.

![parameter](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/parameter.JPG)



**2- Data Ingestion using Https**

To try the data ingestion from HTTP. I created the JSON file that has links to the datasets.

---
> To review my JSON file, download it from my repo.
---

I used Lookup, ForEach, and copy activities for the creation of the pipeline.

![lookup with for each](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/lookup%20with%20for%20each.JPG)

below is the screenshot of the successful run of the pipeline

![lookup proof](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/lookup%20proof.JPG)

then, I created a Scheduled trigger to check how the pipeline works with triggers

![schedulled trigger proof](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/schedule%20trigger%20proof.JPG)


## Azure Data Transformation

After successfully creating pipelines and copying all relevant data in the DataLake Gen2.


**1- Azure DataFlow**

Now, I have to transform the data 

*   Our first requirement for the transformation of the dataset.

![dataflow objective](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/dataflow1.JPG)


I created the Dataflow in AzureDataFactory and used source, filter, select, pivot, lookup, and sink transformation to get the desired results and used dataflow pipeline activity to run it.

![dataflow1](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/dataflow1.JPG)


*   Our second requirement for the transformation of the dataset.

![dataflow2 objective](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/dataflow2%20objective.JPG)


I again created the Dataflow in AzureDataFactory and used advanced transformations like conditional split, aggregate, derived, sort along with source, filter, select, pivot, lookup, and sink transformation to get the desired results and use the dataflow pipeline activity to run it.

![dataflow2](https://github.com/Muhammad1umer-tech/Tokyo-Olympic-Microsoft-Azure/blob/main/images/dataflow2.JPG)



















