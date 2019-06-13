# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Create a Virtual machine using Azure Portal

Students can just read through the tasks and get a feel for how they work or actually step through them like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

You require need an Azure subscription to perform these steps. If you don't have one you can create one by following the steps outlined on the [Create your Azure free account today](https://azure.microsoft.com/en-us/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=docs&utm_campaign=visualstudio) webpage.

**Steps**

**1.** Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com/)

**2.** Choose **Create a resource** in the upper left-hand corner of the Azure portal.

**3.** In the search box above the list of Azure Marketplace resources, search for and select **Windows Server 2016** **Datacenter**, then choose **Create**.

**4.** In the **Basics** tab, under Project details, make sure the correct subscription is selected and then choose to **Create new resource group**. Type ***myResourceGroup*** for the name.

**5.** Under **Instance details**, type ***myVM*** for the Virtual machine name and select Location. Leave the other defaults.

*Although is not needed, increasing VM size is highly recommended in order to speed up process of installing IIS role.*

**6.** Under the **Administrator account** section, provide a username, such as ***azureuser*** and a password. The password must be at least 12 characters long and meet the defined complexity requirements.

**7.** Under **Inbound port** rules, choose **Allow selected ports** and then select **RDP (3389)** and **HTTP (80)** from the drop-down. These are to allow us to connect to the virtual machine using RDP over port 3389 and then to see a web page display over HTTP on port 80.

**8.** Go to the Management tab and under the **Monitoring** section under **Boot diagnostics** select **Off**

**9.** Leave the remaining defaults and then select the **Review + create** button at the bottom of the page.

**10.** Once Validation is passed click the **Create** button. It can take approx three to five minutes to deploy the virtual machine.

**11.** Once the virtual machine is created, go to the resource group you placed the virtual machine in, and open up the virtual machine, then click the **Connect** button on the virtual machine properties page.

**Note**: *The following directions tell you how to connect to your VM from a Windows computer. On a Mac, you need an RDP client such as this Remote Desktop Client from the Mac App Store and on Linux virtual machine you could connect directly from a bash shell using ssh.*

**12.** In the **Connect to virtual machine** page, keep the default options to connect by DNS name over port 3389 and click **Download RDP File**.

**13.** Open the downloaded RDP file and click **Connect** when prompted.

**14.** In the **Windows Security** window, select **More choices** and then **Use a different account**. Type the username as localhost\username, (you could also type **.\azureuser**) enter password you created for the virtual machine, and then click **OK**.

**15.** You may receive a certificate warning during the sign-in process. Click **Yes** or to create the connection and connect to your deployed VM. You should connect successfully.



**!!! Congratulations! You have deployed and connected to a Windows Server virtual machine in Azure. !!!**



If you wish and have time you could also make the deployed server a functioning web server and make a web page available publicly, by continuing with the following steps



**16.** Open up a PowerShell command prompt on the virtual machine, by clicking the **Start** button, typing **PowerShell** right clicking **Windows PowerShell** in the menu and selecting **Run as administrator**

**17.** Install the **Web-Server** feature in the virtual machine by running the following command in the PowerShell command prompt: PowerShell

```PowerShell
Install-WindowsFeature -Name Web-Server -IncludeManagementTools -IncludeAllSubFeature
```

 **18.** When completed you should see a prompt stating **Success** with a value **True**, among other items in the output. You do not need to restart the virtual machine to complete the installation. Close the RDP connection to the VM.

**19.** Back in the portal, select the VM and in the overview pane of the VM, use the **Click to copy** button to the right of the IP address to copy it and paste it into a browser tab.

**20.** The default IIS Web Server welcome page will open, and is available to connect to publicly via this IP address, or via the fully qualified domain name.



**!!! Congratulations! You have created a web server that can be connected to publicly via this IP address, or via the fully qualified domain name. If you had a web page to host you could deploy those source files to the virtual machine and host them for public access on the deployed virtual machine. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*