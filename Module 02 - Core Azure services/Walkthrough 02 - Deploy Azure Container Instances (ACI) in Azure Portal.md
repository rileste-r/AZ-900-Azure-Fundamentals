# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Deploy Azure Container Instances (ACI) in Azure Portal

Students can just read through the tasks and get a feel for how they work or actually step through them like a lab task.

Another option could be to complete the walkthrough at the end of the module,  and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

An active Azure subscription is required. If you do not have an Azure subscription, create a [free Azure account](https://azure.microsoft.com/free/) before you begin.

**Steps**

**1.** To create a new Azure Container Instance sign in to the Azure Portal. Choose **Create a resource** in the upper left-hand corner of the Azure portal and locate the ***Container Instances*** service , then select **Create**. Alternatively, go to the URL https://portal.azure.com/#create/microsoft.containerinstances and when prompted, sign into Azure Portal.

**2.** Provide the following basic details for the new container instance. The UI you encounter may be slightly different compared to the screenshots in this walkthrough, depending on if you accessed the Create New Container Instance via the *Azure portal* or via provided *URL* above, however the details provided will be the same.

- **Container name**: mycontainer
- **Container image type**: Public
- **Container image**: microsoft/aci-helloworld
- **Subscription**: Choose your subscription
- **Resource group**: Select **Create new**, then type myResourceGroup, and select **OK**
- **Location**: Use the dropdown to choose the Azure region

**3.** On the Networking tab, configure the new container instance as follows

- **DNS name label**: Specify a DNS name label for your container. The DNS name label you specify must be unique within the Azure region where you create the container instance. Your container will be publicly reachable at http://<dns-name-label>.<region>.azurecontainer.io. If you receive a **DNS name label not available** error message, specify a different DNS name label

- Leave all other settings in the **Configuration** pane at their default values.

- Select **Review + create** to start the automatic validation process

**4.** When the validation process has passed, review the configuration summary, and select the **Crate** button to begin deploying the container

**5.** When the deployment starts, a notification appears in Azure Portal indicating the deployment is in progress. Another notification is displayed when the container deployment has completed successfully. Wait for the deployment succeeded notification *before* going to Step 6.

**6.** Obtain the Fully Qualified Domain Name (FQDN), in Azure Portal, by opening the **Overview** pane for the container group and navigating to **Resource Groups** > **myResourceGroup** > **mycontainer**. Make a note of the **FQDN** of the container instance, as well its **Status**.

**7.** When the **Status** value of the container instance is Running, navigate to the container's FQDN in a web browser.

**Note**: You can also navigate to the container's IP address in your browser. You can obtain the IP address by following Step 6, and making a note of the **IP address** instead of the **FQDN**.



**!!! Congratulations! You have used Azure Portal to deploy an application to a container in Azure Container Instances successfully. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*