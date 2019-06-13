# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Create a SQL database

Students can just read through the tasks and get a feel for how it works or actually step through it like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

You require need an Azure subscription to perform these steps. If you don't have one you can create one by following the steps outlined on the [Create your Azure free account today](https://azure.microsoft.com/en-us/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=docs&utm_campaign=visualstudio) webpage.

**Steps**

**1.** Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com/)

**2.** Select **Create a resource** on the upper left hand side of the Azure Portal. Select **Databases** and then **SQL Database**. On the page **Create SQL Database**, on Basics tab, fill the fields based on following parameters. In the **PROJECT DETAILS** enter following information:

- **Subscription:** Select your subscription 

- **Resource group:** Select **Create new**, enter **sqldb1-rg1**, then select **OK**. 

**3.** In the **DATABASE DETAILS** pane, enter **db1** as database name and **Create a new** for a SQL Server. Complete the New server pane using below details and click **Select** when finished.

- **Server name:** This needs to be a unique name
- **Server admin login:** Define admin username, such as *azureuser*
- **Password:** Enter a password that meets the complexity requirements
- **Location:** Select Azure location
- All other setting leave on defaults and select **Next : Additional Settings**

**4.** On the **Additional Settings** tab select **Sample** under **DATA SOURCE > User existing data**

**5.** Select **Review + Create** and click to **Create** to deploy and provision the resource group, server, and database. It can take approximately 2 to 5 minutes to deploy.

**Note**: *This database uses the DTU-based purchasing model, but there is another, the vCore-based purchasing model, which is also available.*

**6.** Once complete verify the successful deployment by going to the resource group you just created in the Azure Portal and verifying the presence of the server and database.

**7.** Open the SQL database you created, go to the **Query Editor (preview)** in the left hand pane, and enter the login details and password, then click **OK**

**8.** Once you log in successfully the query pane appears, enter the following query into the editor pane

```T-SQL
SELECT TOP 20 pc.Name as CategoryName, p.name as ProductName FROM SalesLT.ProductCategory pc JOIN SalesLT.Product p ON pc.productcategoryid = p.productcategoryid 
```

**9.** Select **Run**, and then review the query results in the **Results** pane. The query should run successfully.



**!!! Congratulations! You have created a SQL database in Azure and successfully queried the data in that database. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*