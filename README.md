# 🛠️ Microsoft Fabric Demo Project

## 🚀 Project Overview
This end-to-end Microsoft Fabric project illustrates a medallion data pipeline—from ingesting GitHub files to a Power BI report—using a small sample dataset. It leverages best practices including separate workspaces and Lakehouses for different data zones.

**Pipeline flow:**
1. **Workspace & Lakehouse setup**  
   - Created a **Fabric workspace** for development.  
   - Within workspace, created two Lakehouses:  
     - **Bronze Lakehouse**: for raw ingestion  
     - **Silver Lakehouse**: for cleansed data

       <img width="1822" height="814" alt="image" src="https://github.com/user-attachments/assets/6e71a0c8-c2a5-4ac6-a9ea-8fa696d7962f" />


2. **Ingestion Pipeline (Bronze)**  
   - **Lookup activity** reads file list from GitHub folder  
   - **ForEach** iterates each file  
   - **Copy activity** loads files into Bronze Lakehouse

     <img width="1906" height="704" alt="image" src="https://github.com/user-attachments/assets/fde32b4a-be17-412a-9024-80b54db37509" />


3. **Transformation (Bronze → Silver)**  
   - Created Fabric **notebook** using **PySpark + Data Wrangler**  
   - Cleans data (nulls, types, format)  
   - Wrote cleaned data as Delta tables to **Silver Lakehouse**
     Open the Fabric notebook:  
  [🔗 *Transfromation Notebook*](Transformation.ipynb)  
  

4. **Semantic Modeling & Reporting**  
   - Defined semantic model on Silver tables using Fabric modeling  
   - Built demo `Power BI` report (.pbix) with small dataset

     <img width="1321" height="744" alt="image" src="https://github.com/user-attachments/assets/1ba62e4d-fe4a-4080-bfff-2ded0ef2706d" />


---

