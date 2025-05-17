# Building an End to End Data Engineering Solution with Azure  
I have built the End-to-end Azure Data Engineering project using the latest technologies like Azure Data Factory, Databricks, PySpark, Azure Data Lake, and CI/CD with Azure DevOps.  
Dataset - Paris 2024 Olympics Summer games (https://www.kaggle.com/datasets/piterfm/paris-2024-olympic-summer-games)     

 ![Archiecture of Azure End to End Project](https://github.com/shrishtibit/AzureProjectWithCICD/blob/main/Project%20Architecture.jpg)

 # Architecture Overview
Step 1: Setting Up the Azure Environment ⚙️
To start, the following Azure resources were provisioned:

Azure Data Factory (ADF): Used for data orchestration and automation.
Azure Storage Account: Acts as the data lake, storing raw (bronze), transformed (silver), and curated (gold) data.
Azure Databricks: Performs data transformations and computations.

All resources were configured with proper Identity and Access Management (IAM) roles to ensure seamless integration and security.
![image](https://github.com/user-attachments/assets/04f72eba-e344-49f4-b5a6-e186b13340a4)

