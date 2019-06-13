# AZ-900: Module 02 Demo - Azure core services

#### Walkthrough - Add IoT device to Azure IoT Hub

Students can just read through the tasks and get a feel for how it works or actually step through it like a lab task.

Another option could be to complete the walkthrough at the end of the module, and complete all or some of the walkthroughs in the module together at that stage, like an end of module or even end of course lab.

**Prerequisites**

An active Azure subscription is required. If you do not have an Azure subscription, create a [free Azure account](https://azure.microsoft.com/free/) before you begin.

**Steps**

**1.** To create a new Azure IoT Hub, to go to the URL https://portal.azure.com/#create/microsoft.iothub and sign into Azure Portal, when prompted.

**2.** Fill in the fields with the following details.

- **Subscription**: Select the subscription to use for your new Azure IoT Hub.

- **Resource Group**: Choose **Create new** and provide a name for the resource group.

- **Region**: Select the Azure region that is closest to your location from the dropdown list.

- **IoT Hub Name**: Put in a name for your Azure IoT Hub. This name must be unique to your chosen region. If the name you enter is available, a green check mark appears.

- Select the **Next: Size and scale** button to continue.

**3.** On the **Size and scale** tab, use the dropdown list to set the **Pricing and scale tier** to F1 - Free tier.

- Leave all other options set to their defaults.

- Select the **Review + create** button at the bottom.

**4.** Review your choices on the **Review + create** tab, then select the **Create** button to begin creating your new Azure IoT Hub.

**Note**: *When the deployment starts, a notification appears in Azure Portal indicating the deployment is in progress. Another notification is displayed when the deployment has completed successfully.*

**5.** When the deployment has completed, choose **Go to resource** from the notification area to open the Azure IoT Hub **Overview** blade. You can also select **All resources** from the main menu, then choose your Azure IoT Hub from the list of resources.

**6.** To add a new IoT device, select **Explorers** > **IoT Devices** from the **IoT Hub navigation** blade. Then, choose the **+ Add** button.

**7.** Provide a name for your new IoT device, for example myDeviceId, and select the **Save** button. This will create a new IoT device identity in your Azure IoT Hub.

**8.** After the new device is created, select the new device from the list of IoT devices in the **IoT devices** pane. Copy the **Primary Connection String** value. You will use this key in Step 10 to authenticate a connection to a Raspberry Pi device.

**9.** In a web browser, open the [online Raspberry Pi simulator](https://azure-samples.github.io/raspberry-pi-web-simulator/) at https://azure-samples.github.io/raspberry-pi-web-simulator/#Getstarted . Select “**X**” to close the **Overview of Raspberry Pi Simulator** window or choose **Next** to step through the guide.

**10.** In the coding area, make sure that you are working on the default, Microsoft sample code. Replace the placeholder code on Line 15 with the Azure IoT Hub connection string value that you copied from Step 8. Copy over the text that is present, including the brackets.

**11.** Select **Run** or type npm start to run the application. The console output should show the sensor data and messages that are sent from the Raspberry Pi simulator to your Azure IoT Hub. Data and messages are sent each time the Raspberry Pi simulator LED flashes. Select **Stop** to stop sending data.

**12.** To view metrics for the messaging activity in Azure Portal, select **All resources** from the main menu. Choose your Azure IoT Hub from the list of resources. Scroll down to the **IoT Hub Usage** pane of the **IoT Hub Overview** blade. To access these metrics from the **IoT Hub navigation** blade, select **Metrics** from the **Monitoring** section.



**!!! Congratulations! You have set up Azure IoT Hub to collect sensor data from an IoT device. !!!**

------

**Note**: *Remember to remove any newly created Azure resources that you no longer use. Removing unused resources ensures you will not incur unexpected costs. Remove unused resources by deleting the Resource Group that the unused resources belong to.*