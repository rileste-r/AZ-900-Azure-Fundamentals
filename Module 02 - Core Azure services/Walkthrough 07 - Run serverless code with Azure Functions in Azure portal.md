# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Run serverless code with Azure Functions in Azure portal

Students can just read through the tasks and get a feel for how it works or actually step through it like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

An active Azure subscription is required. If you do not have an Azure subscription, create a [free Azure account](https://azure.microsoft.com/free/) before you begin.

**Steps**

**1.** To create a new Azure Function App, sign in to the Azure Portal and select **Create a resource** on the upper left hand side of the Azure Portal. In the search box type **Function App**, and on the page **Function App**, click to **Create**, or alternatively, go to the URL <https://portal.azure.com/#create/Microsoft.FunctionApp> and when prompted, sign into Azure Portal.

**2.** Fill in the Azure Function App settings fields with the following details

- **App name**: Provide a unique name that identifies your new Function App

- **Subscription**: Select an Azure subscription for your Function App

- **Resource Group**: Choose **Create new**. Provide a unique name for your new Resource Group, if Azure has not provided a name automatically

- **OS**: Select Windows. For Linux hosting, see [Create your first function running on Linux using the Azure CLI](https://docs.microsoft.com/en-us/azure/azure-functions/functions-create-first-azure-function-azure-cli-linux) at https://docs.microsoft.com/en-us/azure/azure-functions/functions-create-first-azure-function-azure-cli-linux

- **Hosting plan**: Choose Consumption plan. With Azure serverless hosting, you only pay for the time that your functions run. Using the default **Consumption Plan** means that resources are added dynamically as required by your functions

- **Location**: Choose the Azure location

- **Runtime stack**: Select .NET (this is suitable for running C# and F# functions).

- **Storage**: Choose **Create new**. Provide a unique name for your new storage account, if Azure has not provided a name automatically.

- **Application Insights**: Leave this set to the default value, provided by Azure automatically.

**3.** Select the **Create** button to begin provisioning and deploying your new Azure Function App.

**Note**: *When the deployment starts, a notification appears in Azure Portal indicating the deployment is in progress. Another notification is displayed when the deployment has completed successfully.*

**4.** When the deployment has completed, choose **Go to resource** from the notification area to view your new Azure Function App. You can also select **All resources** from the main Azure menu, then choose your Azure Function App from the list of resources.

**5.** To create an *HTTP Triggered Function*, use the down arrow icon to expand your Azure Function App. Select the “**+**” button next to **Functions**. Choose **In-portal**, and select **Continue**.

**6.** Choose **WebHook** **+ API**, and then select **Create**.

**7.** Select **</> Get function URL** from the within the function editor. Set the **Key** value to default (Function key) using the dropdown. Then, select **Copy** to copy the function URL.

**8.** Paste the copied function URL into your web browser's address bar. Append &name=<yourname> to the end of the URL.

**Note**: *Here, <yourname> refers to your given first name. Navigate to the URL to see the “Hello” message, followed by the name you provided, displayed in your browser. The URL should be similar to https://azfuncek01.azurewebsites.net/api/HttpTrigger1?code=X9xx9999xXXXXX9x9xxxXX==&name=glen*

**9.** When your function runs, trace information is written to log files in Azure. To view the logs in Azure portal, return to the function editor, and select the **Logs** button.



**!!! Congratulations! You have written and run serverless code inside an Azure Function App, in Azure portal, successfully. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*