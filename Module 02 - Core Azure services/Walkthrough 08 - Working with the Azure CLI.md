# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Working with the Azure CLI

Students can just read through the tasks and get a feel for how it works or actually step through it like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

- You require need an Azure subscription to perform these steps. If you don't have one you can create one by following the steps outlined on the [Create your Azure free account today](https://azure.microsoft.com/en-us/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=docs&utm_campaign=visualstudio) webpage.

- A local environment is also needed such as a Windows, Linux or MacOS

**Note**: *The following steps are based on a Windows installation, however they could equally be applicable to a Mac or Linux environment. However there are specific installation steps for each environment. To see the installation steps for your particular environment see the [Install the Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli) page.*

**Steps**

We will install Azure CLI on the Windows operating system using the MSI installer:

**1.** To download the Azure CLI msi, click on the URL <https://aka.ms/installazurecliwindows>, and in the browser, select to **Run**.

**2.** In the installation wizard, accept the license terms, and then click **Install**.

**3.** In the **User Account Control** dialog, select **Yes**.

**4.** Once successfully installed, the Azure CLI is run by opening a Bash shell for Linux or macOS, or from the command prompt or PowerShell for Windows. Open a command prompt as administrator.

**5.** Login to your Azure subscription by running the below command and following the prompts

```
az login 
```

**6.** Verify your installation by running the version check command and ensuring it runs successfully:

```
az --version
```

 **Note**: *Running Azure CLI from PowerShell has some advantages over running Azure CLI from the Windows command prompt. PowerShell provides more tab completion features than the command prompt.*

**7.** Create a resource group to deploy your resources to, by running the following command:

```
az group create --name <resource group name> --location <your nearest datacenter> 
```

**8.** We will now deploy a virtual machine and configure it using an Azure Resource Manager template. The template is available on GitHub at the location <https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.json>, and we will call the script using an Azure CLI command and some other parameters.

**9.** Before deploying we will validate the template and command by running the following Azure CLI command, substituting the values with your own, specifying a username and password and a unique name for the virtual machine DNS label prefix value. The command should run successfully without error, identify what is causing the error, modify it and run the command again until it does validate successfully.

```
az group deployment validate --resource-group <resource group that you have created earlier> --template-uri https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.json --parameters adminUsername=$USERNAME --parameters adminPassword=$PASSWORD --parameters dnsLabelPrefix=$DNS_LABEL_PREFIX
```

**10.** Deploy the resource by running the following command, substituting the same values as earlier:

```
az group deployment create --name MyDeployment --resource-group <resource group that you have created and tested earlier> --template-uri https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.json --parameters adminUsername=$USERNAME --parameters adminPassword=$PASSWORD --parameters dnsLabelPrefix=$DNS_LABEL_PREFIX
```

**11.** Verify the deployment by signing into the Azure portal at [https://portal.azure.com](https://portal.azure.com/)

**12.** Go to the resource group you created and verify the virtual machine and resources are present

**13.** It is also possible to use the Azure CLI with the **Azure Cloud Shell**. The **Azure Cloud Shell** has the Azure CLI already installed. Open the **Azure Cloud Shell** by clicking on the *Azure Cloud Shell icon* in the top right of the Azure Portal

**14.** The browser becomes split and the Azure cloud Shell opens in the bottom half of your existing browser and you are prompted to select between **Bash** or **PowerShell**, select **Bash**

**15.** You are prompted to create storage, select **Create storage**, and allow the Azure Cloud Shell to initialize. You do not need to sign into the Azure Clod Shell, it does this automatically for you.

**16.** Obtain a list of the virtual machines present in your subscription, and display only the resource group and virtual machine name by running the command:

```
az vm list --query [].[resourceGroup,name] --out tsv 
```



**!!! Congratulations! You have installed the Azure CLI on your local machine, created a virtual machine using the Azure CLI and an Azure Resource Manager template, then verified that deployment using the Azure CLI in the Azure Cloud Shell. !!!**

------

**Note**: *Don't forget to delete any resources you deployed to avoid incurring additional costs from them.*

