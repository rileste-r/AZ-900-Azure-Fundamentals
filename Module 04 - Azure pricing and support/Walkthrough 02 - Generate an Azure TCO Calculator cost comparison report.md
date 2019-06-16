# AZ-900: Module 04 Demo - Azure pricing and support

#### Walkthrough - Generate an Azure TCO Calculator cost comparison report

Students can just read through the tasks and get a feel for how they work or actually step through them like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Steps**

**1.** In a browser, navigate to the [Total Cost of Ownership (TCO) Calculator](https://azure.microsoft.com/en-us/pricing/tco/calculator/) webpage, https://azure.microsoft.com/en-us/pricing/tco/calculator/.

**2.** To add details of your on-premises server infrastructure, select **+ Add server workload** in the **Servers** pane.

**3.** Provide a name for your server workloads definition. This example uses the name **Servers: Windows VMs**. Enter the following details into the TCO Calculator.

- **Workload**: Windows/ Linux server 

- **Environment**: Virtual machines 

- **Operating system**: Windows 

- **VMs**: 500

- **Virtualization**: VMware

- **Core(s)**: 8

- **RAM**: 16

- **Optimize**: CPU 

**4.** Select **+ Add server workload** to make a row for a new server workloads definition. Provide a name for the server workloads definition. This example uses the name **Servers: Linux VMs**. Enter the following details into the TCO Calculator.

- **Workload**: Windows/ Linux server
- **Environment**: Virtual machines 

- **Operating system**: Windows 

- **VMS**: 500

- **Virtualization**: VMware

- **Core(s)**: 8

- **RAM**: 16

- **Optimize**: CPU 

**5.** This example definition does not require a database. Leave the **Databases** pane empty. In the **Storage** pane of the TCO Calculator, provide a name for your storage infrastructure definition. Enter the following details into the TCO Calculator.

- **Storage type**: Local Disk/SAN  

- **Disk type**: HDD

- **Capacity**: 60 TB 

- **Backup**: 0 TB 

- **Archive**: 0 TB 

**6.** In the **Networking** pane of the TCO Calculator, enter the following details, then select **Next**.

- **Outbound bandwidth**: 15 TB 

**7.** Explore the options and make any adjustments that you require. The currency used in this example is Euros. No other adjustments are required by this example. Select **Next**, at the end of the page.

**8.** Review the Azure cost saving recommendations and visualizations in the TCO calculator report. This example requires you to adjust the **Timeframe** to **3 years**, and the region to **North Europe**.

**9.** To modify the information you provided to the TCO calculator, go to the bottom of the page, and select **Back**. To save or print a PDF copy of the report select **Download**.



**!!! Congratulations! You downloaded a cost comparison report from the TCO Calculator in Azure. !!!**