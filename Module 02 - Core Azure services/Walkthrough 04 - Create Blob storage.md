# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough – Create Blob storage

Students can just read through the tasks and get a feel for how it works or actually step through it like a lab task.

Another option could be to complete the walkthrough at the end of the module,  and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

You require need an Azure subscription to perform these steps. If you don't have one you can create one by following the steps outlined on the [Create your Azure free account today](https://azure.microsoft.com/en-us/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=docs&utm_campaign=visualstudio) webpage.

**Steps**

**1.** Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com/)

**2.** Select **All services** on the upper left hand side of the Azure Portal. In the **All services** filter box, type **Storage Accounts**. As you begin typing, the list filters based on your input. Select **Storage Accounts**.

**3.** On the **Storage Accounts** window that appears, if there are no storage accounts present you can select **Create storage account**, or if there are already storage accounts present, this option will not be present and you can choose the option **+ Add**.

**4.** Complete the Create storage account blade with the following details

- **Subscription:** Select your subscription
- **Resource group:** Select **Create new**, enter **strac-rg1**, then select **OK**. 
- **Storage account name:** This must be between 3-24 characters in length, can be numbers and lowercase only, and must be unique across Azure
- **Location:** Select your location  
- **Performance** Standard 
- **Account kind:** Leave the default value StorageV2 (general purpose v2) 
- **Replication:** Locally redundant storage (LRS)
- **Access tier:** (default) Hot 

**5.** Select **Review + Create** to review your storage account settings and allow Azure to validate the configuration. Once validated select **Create**.

**6.** Verify its successful creation by going to the resource group just created and locate the storage account.

**7.** Open the storage account and scroll in the left menu for the storage account, scroll to the **Blob** service section, select **Blobs** and then select the **+ Container** button.

**8.** Configure the blob container as belwo and select OK when complete to create the blob container.

Setting Value Name i.e. **blob1** The container name must be lowercase, must start with a letter or number, and can include only letters, numbers, and the dash (-) character. public access level leave the default value i.e. The default level is **Private (no anonymous access)** 

**9.** The container should be created and available

**10.** We will upload a block blob to your new container. Select the container to show a list of blobs it contains. Since this container is new, it won't yet contain any blobs

**Note**: *Block blobs consist of blocks of data assembled to make a blob. Most scenarios using Blob storage employ block blobs. Block blobs are ideal for storing text and binary data in the cloud, like files, images, and videos.*

**11.** Create a .txt file on your local machine, named **blob1.txt**, and enter some text into it, such as this is a blob file or something like that.

**12.** Select the **Upload** button to upload a blob to the container. Browse your local file system to find the file you created in the previous steps to upload as a block blob, Click on the **Advanced** arrow, leave the default values as they are, just note them, and then select **Upload**.

**Note**: *You can upload as many blobs as you like in this way. You'll see that the new blobs are now listed within the container.*

**13.** View the uploaded block blob by right clicking on the blob file that was uploaded and selecting **View/edit blob**

**14.** You can download a block blob by right clicking on the block blob and selecting **Download**. The blob file opens in a browser and is then downloadable by right clicking on the file and selecting save as



**!!! Congratulations! You have created a storage account, created a blob storage container within that storage account, then uploaded a block bob, viewed and edited the block blob in the blob container and then downloaded the block blob. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*