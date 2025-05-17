# Building an End to End Data Engineering Solution with Azure  
I have built the End-to-end Azure Data Engineering project using the latest technologies like Azure Data Factory, Databricks, PySpark, Azure Data Lake, and CI/CD with Azure DevOps.  
Dataset - Paris 2024 Olympics Summer games (https://www.kaggle.com/datasets/piterfm/paris-2024-olympic-summer-games)   

 # Project Architecture

 ![Archiecture of Azure End to End Project](https://github.com/shrishtibit/AzureProjectWithCICD/blob/main/Project%20Architecture.jpg)

 # Architecture Overview
**Step 1: Setting Up the Azure Environment** ⚙️   

To start, the following Azure resources were provisioned:      

- **Azure Data Factory (ADF)**: Used for data orchestration and automation.    
- **Azure Storage Account**: Acts as the data lake, storing raw (bronze), transformed (silver), and curated (gold) data.     
- **Azure Databricks**: Performs data transformations and computations.     
    
All resources were configured with proper Identity and Access Management (IAM) roles to ensure seamless integration and security.  

![image](https://github.com/user-attachments/assets/04f72eba-e344-49f4-b5a6-e186b13340a4)  
   
**Step 2: Implementing the Data Pipeline Using ADF** 🚀   

Azure Data Factory (ADF) serves as the backbone for orchestrating the data pipeline.

Dynamic Copy Activity:
- ADF pulls data from GitHub using an HTTP connector and stores it in the bronze container in Azure Storage.
- Parameters were added to the pipeline for adaptability to changes in the data source.
 
![image](https://github.com/user-attachments/assets/b86e56e0-f844-4ff9-8c31-e1d0209b5488)

-The raw data is now securely stored and ready for transformation.    

![image](https://github.com/user-attachments/assets/0d6f965d-cbc4-48c0-83a1-c81e4721f40c)   

**Step 3: Data Transformation with Azure Databricks** 🔄      
Using Azure Databricks, the raw data from the bronze container was transformed into a structured format.       

**Key Steps**:
- Cluster Setup: A Databricks cluster was created to process the data efficiently.
- Data Lake Integration: Databricks connected to Azure Storage to access the raw data.
  
**Transformations**
- Replacing null values in the following columns with respective default values
- Filtering dataframe based on multiple conditions
- Casting columns to appropriate data types
- Sorting dataframe based on multiple columns
- Calculating cumulative sum of weights on specific column
- Grouped and concatenated data to make it more usable for analysis

![image](https://github.com/user-attachments/assets/8b702e18-ca2f-42b4-851a-2c0f1e658ebd)

Created Dynamic Parameterized notebook using DB utils  

![image](https://github.com/user-attachments/assets/7f5ffbf9-940c-4008-b262-e0ffce05fa26)     

Built a Workflow job in Databricks for Data orchestration from bronze to the silver container   

![image](https://github.com/user-attachments/assets/3b5b4a0e-ee8f-4381-958b-fb1f50289fa1)  

Saved the transformed data in the silver container in Parquet format for optimal storage and query performance  

![image](https://github.com/user-attachments/assets/24d163b6-5d50-4253-8e75-4b416613cb1a)   

**Step 4- Creating Delta Live Tables and DLT pipelines for Curated Entities in Gold Layer**  

- Created Delta Live Tables in Databricks for Curated Entities

  ![image](https://github.com/user-attachments/assets/ada2e279-4633-4f6e-a578-7d5306148954)

- Creating End to End DLT Pipeline for moving the enriched data to gold layer

  ![image](https://github.com/user-attachments/assets/435797e2-8508-4382-b127-a6c6227a7701)











  












