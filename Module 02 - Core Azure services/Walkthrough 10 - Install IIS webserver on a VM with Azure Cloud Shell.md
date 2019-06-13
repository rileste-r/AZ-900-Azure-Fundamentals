# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Install IIS webserver on a VM with Azure Cloud Shell

Students can just read through the tasks and get a feel for how it works or actually step through it like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

An active Azure subscription is required. If you do not have an Azure subscription, create a [free Azure account](https://azure.microsoft.com/free/) before you begin.

**Steps**

**1.** To access **Azure Cloud Shell** go to the location [https://shell.azure.com](https://shell.azure.com/) and sign in with your Azure user login credentials.

You can also run Azure Cloud Shell from within Azure Portal by using the Cloud Shell icon.

**2.** If prompted, choose a **Bash** or **PowerShell** environment. This walkthrough uses **PowerShell**.

**3.** First time Azure Cloud Shell users must create and configure Cloud Drive storage, to allow Azure Cloud Shell files to persist. To create and configure storage, select **Show advanced settings**. If you have created and configured storage already, go to Step 5.

**4.** Provide the following details to create and configure storage.

- **Subscription**: Choose your subscription

- **Cloud Shell region**: Select the location closest to you. For example, North Europe

- **Resource group**: Choose **Create new**, then provide a unique name for your new resource group.

- **Storage account**: Select **Create new**, and provide a unique name for your storage account.

- **File share**: Choose **Create new**, then enter a unique file share name.

- Select the **Create storage** button

Wait for the storage setup to complete. When the storage setup is complete, the **Welcome to Azure Cloud Shell** message is shown in the terminal window.

**5.** At the Azure Cloud Shell prompt, set a VM administrator username and password with the Get-Credential command. The credentials are assigned to the variable $cred. The variable is recalled when the new VM is created in the next Step 6.

```PowerShell
$cred = Get-Credential
```

When prompted, enter a username and password for the VM administrator. For example,

- **User**: myVMAdmin

- **Password**: pa$$W0rd101

**6.** Create a VM with the New-AzVM command. The following example creates a VM named myVM in the North Europe location. If they do not exist, the resource group myResourceGroup and supporting network resources are created in Azure. To allow web traffic, the following command also opens port 80. Change these to more suitable settings, if you prefer.

**Note**: *Ensure you are signed into your Azure subscription. If you have multiple subscriptions, you can get a list of your subscriptions using the command Get-AzSubscription. Specify which subscription to use with the command Select-AzSubscription -Subscription "<Name of your subscription>". Substitute the actual name of the subscription you want to use for <Name of your subscription>.*

```PowerShell
New-AzVm -ResourceGroupName "myResourceGroup" -Name "myVM" -Location "North Europe" -VirtualNetworkName "myVnet" -SubnetName "mySubnet" -SecurityGroupName "myNetworkSecurityGroup" -PublicIpAddressName "myPublicIpAddress" -OpenPorts 80 -Credential $cred
```

 When the newly created resources and VM are ready, details about the resources and VM will be displayed in the Azure Cloud Shell window. Wait for the resources and VM to be created.

**7.** Use the Set-AzVMExtension command to install the Custom Script Extension. The Custom Script Extension runs the command powershell Add-WindowsFeature Web-Server to install IIS to your new VM.

```PowerShell
Set-AzVMExtension -ResourceGroupName "myResourceGroup" -ExtensionName "IIS" -VMName "myVM" -Location "North Europe" -Publisher Microsoft.Compute -ExtensionType CustomScriptExtension -TypeHandlerVersion 1.8 -SettingString '{"commandToExecute":"powershell Add-WindowsFeature Web-Server"}'
```

Wait for the Custom Script Extension and IIS to install. When the Custom Script Extension installs IIS successfully, IsSuccessStatusCode will return True in the Azure Cloud Shell window.

**8.** Obtain the public IP address of your load balancer with the Get-AzPublicIPAddress command. The following example obtains the IP address for *myPublicIPAddress* created in Step 4.

```PowerShell
Get-AzPublicIPAddress -ResourceGroupName "myResourceGroup" -Name "myPublicIPAddress" | select IpAddress
```

 **9.** Use a web browser to navigate to the public IP address. The Windows server **IIS Welcome** page should be displayed in your browser.

**10.** Return to Azure Cloud Shell. Run the following command to remove the resource group myResourceGroup, VM, and all related resources. Choose **Yes** to confirm the deletion, when prompted.

```PowerShell
Remove-AzResourceGroup -Name myResourceGroup
```



**!!! Congratulations! You used Azure Cloud Shell to automate the installation of IIS on a new VM. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*