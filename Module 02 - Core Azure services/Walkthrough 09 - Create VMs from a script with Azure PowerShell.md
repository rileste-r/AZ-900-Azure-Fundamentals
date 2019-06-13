# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Create VMs from a script with Azure PowerShell

Students can just read through the tasks and get a feel for how it works or actually step through it like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

- An active Azure subscription is required. If you do not have an Azure subscription, create a [free Azure account](https://azure.microsoft.com/free/) before you begin.

- Installing the Azure PowerShell module requires *Windows PowerShell* 5.1 or higher on Windows, or *PowerShell Core* 6.0 on Windows, Linux, macOS and ARM. Follow these instructions for [Installing various versions of PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell?view=powershell-6) on your local machine at https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell?view=powershell-6 

- You must have a text editor installed to write a new PowerShell script. You could use the [PowerShell Integrated Scripting Environment (ISE)](https://docs.microsoft.com/en-us/powershell/scripting/components/ise/windows-powershell-integrated-scripting-environment--ise-?view=powershell-6) or another option could be to use [Visual Studio Code](https://visualstudio.microsoft.com/).



**Steps**

**1.** Open a text editor. Make a new file, and add the following code into the new file. The comments explain each of the commands within the script file.

```PowerShell
# capture the input parameter in a variable
param([string]$resourceGroup)

# prompt for a username and password for the VMs admin account
# and capture the result in a variable
$adminCredential = Get-Credential -Message "Enter a username and password
for the VM administrator."

# Add a loop that executes three times to create a new VM for each loop
iteration
For ($i = 1; $i -le 3; $i++)
{
# create a name for each VM, store it in a variable and output it to
the console
$vmName = "AzDemo" + $i
Write-Host "Creating VM: " $vmName

# create a VM using the $vmName variable
New-AzVm -ResourceGroupName $resourceGroup -Name $vmName -Credential $adminCredential -Image UbuntuLTS
}
```

**2.** Save the new file as **azdemo.ps1**. Make a note of the directory location where you save the script file, you will be required to recall the directory location in Step 6.

**3.** Open a new PowerShell session with *elevated* privileges.

- **Windows**: Select the **Start** icon from the task bar. Type **PowerShell**. Right select the **Windows PowerShell Desktop App** icon. Choose **Run as administrator**.

- **Linux and macOS**: In a terminal, launch PowerShell Core with elevated privileges using the following command.

- sudo pwsh 

**4.** At the PowerShell prompt, install the Azure PowerShell module (Az) by running the following command.

```PowerShell
Install-Module Az -AllowClobber
```

Answer **Yes** or **Yes to All**, if prompted, to trust the Az module.

**Note**: *Windows users should agree to install the NuGet provider, and agree to install modules from the PowerShell Gallery (PSGallery), if prompted. If you receive script execution failures, run Set-ExecutionPolicy RemoteSigned in an elevated PowerShell session. Running the command will unrestricted your execution policy, and allow you to install and run modules from the PSGallery.*

**5.** Update the Az module by running the following command.

```PowerShell
Update-Module -Name Az
```

 Answer **Yes** or **Yes to All**, if prompted, to trust updates to the Az module. If you already have the latest version of the Az module installed, the prompt will be returned automatically.

**6.** Use the cd command to change into the directory that contains the PowerShell script file azdemo.ps1 that you created in Step 1. Replace <scriptsdir> with the actual directory where you saved the script file.

```PowerShell
cd C:\<scriptsdir>
```

**7.** Sign into Azure by running the following command. When prompted, provide your Azure login credentials and select the **sign in** button.

```PowerShell
Connect-AzAccount
```

**Note**: *The following Step 8 assumes that you have a single Azure subscription associated with your Azure account. If you have multiple subscriptions, you can get a list of your subscriptions using the command Get-AzSubscription. Specify which subscription to use with the command Select-AzSubscription -Subscription "<Name of your subscription>". Substitute the actual name of the subscription you want to use for <Name of your subscription>.*

**8.** Create a new resource group using the following command.

```PowerShell
New-AzResourceGroup -Name <name> -Location <location>
```

 Replace <name> with a suitable name for the new resource group. For example, AzDemo. Add a value for <location> that corresponds to the Azure region closest to you. For example, northeurope.

**9.** Execute the azdemo.ps1 script by running the following command. Substitute the name of the resource group that you created in the previous Step 8 for <resource group name>.

```PowerShell
.\azdemo.ps1 <resource group name>
```

 **10.** When prompted, provide a username and password for the VM administrator, and select **ok**. For example, for the **User name** enter azdemoadmin and for the **Password** enter pa$$W0rd101.

**11.** The script will begin creating the Azure resources required by each VM, and may take several minutes to complete. Wait for the script to finish before you go to Step 12.

**12.** When the script is finished, verify that it ran successfully by looking at the resources listed in the resource group that you created in Step 8. When you run the following command you should see three VMs, each with a unique name.

```PowerShell
Get-AzResource -ResourceType Microsoft.Compute/virtualMachines
```

 **13.** The suffix AzVM is specific to VM-based commands in Azure PowerShell. 

**14.** When you are finished, use the following Azure PowerShell command to delete the resource group and all the resources within it.

```PowerShell
Remove-AzResourceGroup -Name <Resource group name>
```

 Substitute the name of the resource group you created in Step 8 for <resource group name>. When asked to confirm the deletion, answer **Yes**. The command may take several minutes to complete, and will return **True** when the resource group is deleted successfully.

**15.** Run the following command to disconnect the PowerShell session from your Azure account. Then, exit or close the PowerShell terminal window.

```PowerShell
Disconnect-AzAccount
```

 

**!!! Congratulations! You wrote and ran a local PowerShell script. The PowerShell script used the Azure PowerShell module to create three VMs in Azure from a Linux Ubuntu image. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*