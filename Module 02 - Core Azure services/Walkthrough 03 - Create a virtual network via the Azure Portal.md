# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Create a virtual network via the Azure Portal

Students can just read through the tasks and get a feel for how it works or actually step through it like a lab task.

Another option could be to complete the walkthrough at the end of the module,  and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

You require need an Azure subscription to perform these steps. If you don't have one you can create one by following the steps outlined on the [Create your Azure free account today](https://azure.microsoft.com/en-us/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=docs&utm_campaign=visualstudio) webpage.

**Steps**

**1.** Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com/)

**2.** Choose **Create a resource** in the upper left-hand corner of the Azure portal, then select **Networking** > **Virtual network**

**3.** In the **Create virtual network** pane choose **Create** using the following settings and values.

- **Name:** vnet1

- **Address space:** 10.1.0.0/16

- **Subscription:** Select your subscription

- **Resource group:** Select **Create new**, enter **vnet1-rg1**, then select **OK**.

- **Location:** Select Azure location

- **Subnet – Name:** subnet1

- **Subnet Address range:** 10.1.0.0/24

- Leave the rest of the settings at their default values and select **Create**.

**4.** Verify the creation of the virtual network by going to the newly created resource group and viewing the virtual network is present, you can click on the virtual network and view its properties if you wish.

**5.** Create a virtual machine by going to the the upper-left side of the Azure Portal and selecting **Create a resource** > **Compute** > search for **Windows Server 2016** **Datacenter**

**6.** In **Create a virtual machine** - **Basics** tab, enter or select this information:

- **Subscription:** Select your subscription

- **Resource group:** The resource group you created it in the last section, i.e. **vnet1-rg1**

- **Virtual machine name:** vm1

- **Region:** Same as Virtual Network location

- **Size:** Standard DS2 v3

- **Username:** Define username, such as *azureuser*
- **Password:** Enter a password that will meets the complexity requirements
- **Public inbound ports:** Select **Allow selected ports**

- **Selected inbound ports:** Select **HTTP**, **HTTPS**, **SSH** and **RDP**

**7.** Select **Next** : **Disks**, leave the default values

**8.** Select **Next** : **Networking**, complete the following details

- **Virtual network:** Leave the default **vnet1**

- **Subnet:** Leave the default **subnet1 (10.1.0.0/24)**

- **Public IP:** Leave the default (new) **vm1-ip**

- **NIC network security group:** Accept the default **Basic**

- **Public inbound ports:** Select **Allow selected ports**

- **Select inbound ports:** Select **HTTP**, **HTTPS**, **SSH** and **RDP**

**9.** Select **Next** : **Management**, accept all the default values except for the below settings:

- **Boot diagnostics:** Accept the default value i.e. **On**

- **Diagnostic storage account:** Accept the default value i.e. **vnet1rgdiag**

**10**. Select **Review** + **create**. Azure will validate the configuration. When you see that Validation passed, select **Create**. Deployment times can vary but it can generally take between three to six minutes to deploy.

**11.** Create a second Virtual machine by repeating steps **5 to 9** above, using the same values above above ensuring the below settings are set:

- **Virtual machine name:** vm2

- **Public IP:** Leave the default (new) **vm2-ip**

- **Diagnostic storage account:** Leave the default value i.e. **vnet1rg1diag**

**12.** When finished filling in the details, validate the configuration by clicking **Review + create** and once successfully validated click **Create**

**13.** When both virtual machine have completed deployment connect to the first virtual machine, **vm1**, by going to the resource group you placed the virtual machine in, **vnet-rg1** and open up the virtual machine, then click the **Connect** button on the virtual machine properties page.

**Note**: *The following directions tell you how to connect to your VM from a Windows computer. On a Mac, you need an RDP client such as this Remote Desktop Client from the Mac App Store and on Linux virtual machine you could connect directly from a bash shell using ssh.*

**14.** In the **Connect to virtual machine** page, keep the default options to connect by DNS name over port 3389 and click **Download RDP File**.

**15.** Open the downloaded RDP file and click **Connect** when prompted.

**16.** In the **Windows Security** window, select **More choices** and then **Use a different account**. Type the username as localhost\username, (you could also type **.\azureuser**) enter password you created for the virtual machine, and then click **OK**.

**17.** You may receive a certificate warning during the sign-in process. Click **Yes** or to create the connection and connect to your deployed VM. You should connect successfully.

**18.** Open up a PowerShell command prompt on the virtual machine, by clicking the **Start** button, typing **PowerShell** right clicking **Windows PowerShell** in the menu and selecting **Run as administrator**

**19.** Run the command 

```CMD
ping vm2 
```

You receive an error, saying request timed out. The ping fails, because ping uses the **Internet Control Message Protocol (ICMP)**. By default, ICMP isn't allowed through the Windows firewall.

**20.** To allow *vm2* to ping *vm1* enter the below command. This command allows ICMP inbound through the Windows firewall:

```PowerShell
New-NetFirewallRule –DisplayName “Allow ICMPv4-In” –Protocol ICMPv4 
```

**21.** Connect to *VM2* as has been done for *VM1*, using rdp. i.e. open **vm2** properties and click the **Connect** button to download and then connect vis RDP

**22.** Open up a PowerShell command prompt on the virtual machine VM2, and run the command:

```CMD
ping vm1
```

You should now be able to ping the vm1 virtual machine successfully, because ICMP has been configured to be allowed through the Windows firewall on the *vm1* virtual machine in an earlier step.



**!!! Congratulations! This ping is being done using the *virtual network* you created and deployed the two virtual machines into. The two virtual machines are communicating over this *virtual network* that was created. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*