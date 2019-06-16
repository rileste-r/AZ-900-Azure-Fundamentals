# AZ-900: Module 04 Demo - Azure pricing and support

#### Walkthrough - Generate an Azure Pricing Calculator estimate

Students can just read through the tasks and get a feel for how they work or actually step through them like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Steps**

**1.** In a browser, navigate to the [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/) webpage, https://azure.microsoft.com/en-us/pricing/calculator/.

**2.** To add details of your VM configuration, select **Virtual Machines** from the **Products** tab. Inside the **Virtual Machines added** message dialog, choose **View**.

**3.** Enter a name for your Azure Pricing Calculator estimate, and a name for your VM configuration. This walkthrough example uses **My Pricing Calculator Estimate** for the estimate, and **Windows VM** for the VM configuration.

**4.** Modify the default VM configuration to match the following VM details.

- **Region**: North Europe
- **Operating system**: Windows
- **Type**: (OS Only)
- **Tier**: Standard
- **Instance**: A2: 2 Core(s), 3.5 GB RAM, 135 GB Temporary storage 

**Note**: *The VM instance specifications and pricing may differ from those in this example. Follow this walkthrough by choosing an instance that matches the example as closely as possible. To view details about the different VM product options, choose **Product details** from the **More info** menu on the right.*

**5.** Set the **Billing Option** to **Pay as you go**.

**6.** In Azure, a month is defined as 730 hours. If your VM needs to be available 100 per cent of the time each month, you set the hours-per-month value to 730. This walkthrough example requires one VM to be available 50 per cent of the time each month.

Leave the number of VMs set at 1, and change the hours-per-month value to 365.

**7.** In the **Managed OS Disks** pane, modify the default VM storage configuration by adding the following details.

- **Tier**: Standard HDD 
- **Disk size**: S30: 1024 GiB
- **Number of disks**: 1
- **Snapshot**: Off
- **Storage transactions**: 10,000 

**8.** To add networking bandwidth to your estimate, go to the top of the Azure Pricing Calculator webpage. Select **Networking** from the product menu on the left, then choose the **Bandwidth** tile. Inside the **Bandwidth added** message dialog, select **View**.

**9.** Add a name for your VM bandwidth configuration. This walkthrough example uses the name **Bandwidth: Windows VM**. Modify the default bandwidth configuration by adding the following details.

- **Region**: North Europe 

- **Zone 1: North America, Europe**: 50 GB 

**10.** To add an Application Gateway, return to the top of the Azure Pricing Calculator webpage. From within the **Networking** product menu, choose the **Application Gateway** tile. Inside the **Application Gateway** message dialog, select **View**.

**11.** Add a name for your Application Gateway configuration. This walkthrough uses the name **App Gateway: Windows VM**. Modify the default Application Gateway configuration by adding the following details.

- **Region**: North Europe
- **Tier**: Basic
- **Size**: Small
- **Gateway hours**: 1 x 730
- **Data processed**: 50 GB
- **Zone 1: North America, Europe**: 50 GB 

**12.** Go to the bottom of the Azure Pricing Calculator webpage to view your total **Estimated monthly cost**.



**Note**: E*xplore the various options available within the Azure Pricing Calculator. For example, this walkthrough requires you to update the currency to Euro.*

*Change the currency to Euro, then select **Export** to download a copy of the estimate for offline viewing in Microsoft Excel (.xlsx) format.*



**!!! Congratulations! You downloaded an estimate from the Azure Pricing Calculator. !!!**