# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Save a recommendations report with Azure Advisor

Students can just read through the tasks and get a feel for how it works or actually step through it like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

An active Azure subscription is required. If you do not have an Azure subscription, create a [free Azure account](https://azure.microsoft.com/free/) before you begin.

**Steps**

**1.** Go to the URL https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F101-vm-simple-linux%2Fazuredeploy.json to begin deploying a new VM to Azure from a template. Sign into the Azure Portal, when prompted. The **Visualize** button will bring you to the URL http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F101-vm-simple-linux%2Fazuredeploy.json and provide a visual representation of the deployment you will perform. This visualization is available with all template deployments to Azure and may be helpful when constructing templates and deployments to Azure to allow you view the architecture and relationships between resources.

**2.** Enter the following details for the new VM.

- **Subscription**: Select your Azure subscription.

- **Resource group**: Choose **Create** **new**, and enter a name for the new resource group. Select the **OK** button.

- **Location**: Choose the Azure location

- **Admin Username**: Enter a name for the VM administrator

- **Authentication Type**: Select password.

- **Admin Password Or Key**: Enter a password for the VM administrator.

- **DNS Label Prefix**: Enter a DNS label prefix. For example, *mydnsprefix*

- **Ubuntu OS Version**: Leave this at the default setting. For example, 16.04.0LTS

- **Location**: Leave this at the default setting [resourceGroup().location]

- Check the box to agree to the terms and conditions.

- Select the **Purchase** button.

**Note**: *When the deployment starts, a notification appears in Azure Portal indicating the deployment is in progress. Another notification is displayed when the deployment has completed successfully.*

**3.** When the deployment has completed, choose **Go to resource group** from the notification area to open the Azure resource group **Overview** blade. You can also select **Resource groups** from the main Azure menu, then choose your resource group from the list.

**4.** Verify that the new VM and associated network resources are present in the Azure resource group **Overview** pane.

**5.** Open **Advisor** from the main Azure menu. The **Recommendations** tile under **Overview**, and panels, allow you to filter the recommendations identified by Azure Advisor. For example, for an overview of Security Center recommendations, select the **Security** panel.

**Note**: *Azure Advisor recommendations are unique to your Azure configuration and usage history. More or less recommendations may be available, in accordance with your Azure resource configurations and usage telemetry.*

**6.** Choose **Follow Security** **Center** **Recommendations** to see a list of security center recommendations applicable to your subscription.

**7.** Select a recommendation from the list for more information. The following example shows how to access information about applying disk encryption to VMs. Explore the other recommendations to learn about Azure Advisor.

**8.** To download an Azure Advisor recommendations report, return to the **Azure Advisor Overview**. Select **Download recommendations** as PDF or CSV, and save the report file.



**!!! Congratulations! You created and saved a personalized recommendations report with Azure Advisor. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*