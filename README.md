# 22-Use-Microsoft-Purview-with-Azure-Synapse-Analytics
Microsoft Purview enables you to catalog data assets across your data estate and track the flow of data as it is transferred from one data source to another - a key element of a comprehensive data governance solution.


This lab demonstrates how to use **Microsoft Purview** to catalog and track data lineage in **Azure Synapse Analytics**. You will register data sources, scan and explore metadata, track lineage, and execute a pipeline that moves data from Azure Data Lake to a Synapse dedicated SQL pool.

---

## 🔹 Steps

### 1. Create a Microsoft Purview Account
- In the Azure Portal, create a new **Microsoft Purview account**.

### 2. Launch Purview Studio
- Navigate to your Purview account and open **Purview Studio**.

### 3. Register Data Sources
- Register your **Azure Synapse Analytics Workspace** and other relevant data sources.
- Ensure appropriate permissions are granted (e.g., **Managed Identity**).

### 4. Start a Scan
- Create and start a **scan** on the registered data sources.
- This process catalogs data assets like tables and databases.

### 5. Browse the Data Catalog
- After the scan is complete, explore the discovered assets within the **Data Map**.

### 6. View Lineage (Data Flow Tracking)
- Use the **Lineage** feature to track data movements within Azure Synapse Analytics.
- View how data flows from sources to destinations.

### 7. Access Catalog from Synapse Studio
- In **Synapse Studio**, connect to the Purview catalog.
- Search and query data assets directly from Synapse.

---

## 🔁 Additional Steps - Data Movement and Lineage Tracking

### 8. Create and Run a Pipeline
- In Synapse Studio, go to **Integrate > + > Copy Data Tool**.
- **Source**: Select the `products.csv` file from the Data Lake.
- **Destination**: Choose the `dbo.products` table in the dedicated SQL pool.
- Configure the format settings:
  - File format: `DelimitedText`
  - Column delimiter: `Comma (,)`
  - Row delimiter: `Line feed (\n)`
  - First row as header: ✔️
- Name the task `Load_Product_Data` and use the **Bulk insert** method.
- Deploy and run the pipeline. Wait for the run to succeed.

### 9. Track Lineage in Microsoft Purview
- In Purview Studio, navigate to your collection.
- Filter assets to display **Data pipelines**, **Files**, and **Tables**.
- Select the `Copy_xxx` asset and view the **Lineage** tab.
- Observe data flow from `products.csv` to the `products` table.
- Use "Switch to asset" links to view details of each asset in the lineage.

### 10. Pause Resources and Clean Up
- In Synapse Studio, go to **Manage > SQL Pools** and pause your SQL pool.
- In the Azure Portal, navigate to **Resource Groups**.
- Select your lab resource group (e.g., `dp203-xxxxxxx`) and delete it to avoid unnecessary costs.

---

✅ **Tip**: You can view Purview catalog assets and lineage directly from Synapse Studio using the built-in search integration.

---


## Screenshots
![lab22](https://github.com/user-attachments/assets/592aced5-b5c0-44e3-96db-6a7477099372)
![lab22row100](https://github.com/user-attachments/assets/e612b9df-c8fe-47c8-98a0-5c58a1b59e8f)
![lab22purview](https://github.com/user-attachments/assets/9edc8a0b-89c4-43d3-a226-46e6a2d5abef)
![lab22list](https://github.com/user-attachments/assets/9ae5890a-a87c-48cc-8072-f85dd742c2ac)
![lab22addrole](https://github.com/user-attachments/assets/32274e71-c51c-4918-b35e-4e7cb1887bc4)
![lab22purviewaccount](https://github.com/user-attachments/assets/448d8d19-67d4-4872-96a3-2848990e52b2)
![lab22addrole2](https://github.com/user-attachments/assets/d0c7c87a-cc51-4c88-93b9-df25a6754893)
![lab22code](https://github.com/user-attachments/assets/f537a538-7c21-4fc4-a7d7-c91a8f6b3fce)
![lab22code2](https://github.com/user-attachments/assets/6506cf4f-7fdc-4535-b281-2d2a3bd237b6)
![lab22portal](https://github.com/user-attachments/assets/32a9d260-b398-45ee-8a52-6bc121abd10d)
![lab22purviewdatamap](https://github.com/user-attachments/assets/ef41f427-33b1-4ffe-a995-7ed7a55dda38)
![lab22purviewdatamap2](https://github.com/user-attachments/assets/9c8a48cb-f4ae-4d76-a5b8-e617b56d6566)
![lab22purviewdatamap3](https://github.com/user-attachments/assets/146f4f83-3c73-4444-bbb0-a109f8f04993)
![lab22purviewdatamap4](https://github.com/user-attachments/assets/b54e5598-50a0-42fd-948e-b4d638a5c1d0)
![lab22purviewdatamap5](https://github.com/user-attachments/assets/c083f6ce-ffd9-4731-a602-3820ad61b73f)
![lab226datamap](https://github.com/user-attachments/assets/b370d9d5-30ef-472f-bab6-cdb403fe2326)
![lab227](https://github.com/user-attachments/assets/64a74b4a-e1ae-4294-95a7-d4c9603d0b2e)
![lab228](https://github.com/user-attachments/assets/d9aee268-415c-4a98-bd56-7ead03b9eabf)
![lab229](https://github.com/user-attachments/assets/72e6f0a2-37ed-4aa2-ae91-aaf39c6a77b9)
![lab229pipeline](https://github.com/user-attachments/assets/68473de5-04c9-442d-a224-561176fe3afc)
![lab229pipeline2](https://github.com/user-attachments/assets/8b8b1246-8fef-4892-950a-bf7f5b823af8)
![lab229son](https://github.com/user-attachments/assets/dc42acb0-a496-44e3-b0ae-5f1268a4cfba)
![lab229end](https://github.com/user-attachments/assets/8de4dcf9-c403-4da8-8dcf-5afc2fac7910)
![lab229endd](https://github.com/user-attachments/assets/f8cce2c4-b217-4f01-97a1-eadc30c8ffe3)

