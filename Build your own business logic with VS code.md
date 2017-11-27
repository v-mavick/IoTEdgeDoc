# Build Your Own Business Logic for Azure IoT Edge with VS Code #
In November 2017, we shipping [Azure IoT Edge](https://azure.microsoft.com/en-us/services/iot-edge/) preview version. [Azure IoT Edge](https://azure.microsoft.com/en-us/services/iot-edge/) is an Internet of Things (IoT) service that builds on top of Azure IoT Hub. This service is designed for customers who want to analyze data on devices closer to the source of the data--commonly referred to as "at the edge", instead of in the cloud. By incorporating edge computing into your designs, your IoT devices can make use of business logic at the device level to filter, modify, analyze, and ultimately determine which data is necessary to send to the cloud. By moving parts of your workload to the edge, your devices can spend significantly less time sending messages to the cloud, thus freeing up valuable processing resources allowing your IoT devices to react more quickly to changes in status.

Along with this release, we have published [Azure IoT Edge extension](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-edge) and have updated [Azure IoT Toolkit extension](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-toolkit) These two documents make it easy to code, build, deploy and debug your IoT Edge solutions in Visual Studio Code, by providing a rich set of functionalities which include:
* Creating new IoT Edge projects
* Building and publishing IoT Edge modules
* Debugging IoT Edge modules locally
* Managing IoT Edge devices in IoT Hub
* Deploying IoT solutions to IoT Edge devices
* Stopping and restarting IoT Edge

![](/IoTEdgeExt.png)
## Get Started with IoT Edge in VS Code ##
### Create a simulated Edge Device ###
You can explore the powerful potential of edge computing by deploying Azure IoT Edge on a simulated device. Here are the tutorials for both [Windows](https://docs.microsoft.com/en-us/azure/iot-edge/tutorial-simulate-device-windows) and [Linux](https://docs.microsoft.com/en-us/azure/iot-edge/tutorial-simulate-device-linux) operating environments.
### Develop and deploy a C# IoT Edge module ###
You can create a new IoT Edge module and build your own business logic inside of it. Please see [this tutorial](https://docs.microsoft.com/en-us/azure/iot-edge/tutorial-csharp-module) for more details.
### Debug your IoT Edge C# module ###
1. To start debugging, you will need to use the dockerfile.debug to rebuild your docker image and deploy your Edge solution again.
In VS Code explorer, select **Dockerfile.debug** and right-click to select **Build IoT Edge module Docker image**. Then containerize and publish your module image as usual. It's recommended you use a local registry to host your images for debugging purposes if you are working on a Linux container.
![](/dockImageDebug.png)
2. You can reuse the deployment.json file if you have correct modules and routes for your IoT Edge. In command Palette (Ctrl+Shift+P), type and select Edge: Restart Edge to get your module started in debug version.
3. Configure your launch.json file:


	- If you don't have a launch.json file yet, navigate to the VS Code debug window, press **F5** and select **IoT Edge (.Net Core)**. launch.json file will be generated for you.
	![](/1-add-config-new-launch-json.gif)
	- If launch.json file is already there, open it in VS Code, click **Add Configuration...**, and select **Edge: Debug IoT Edge Module (.NET Core)**.
	![](/1-add-config-existing-launch-json.gif)
4. In launch.json, navigate to the Debug IoT Edge Module (.NET Core) section and specify the <container_name\>.
![](/2-update-container-name.gif)
5. Navigate to Program.cs. Add breakpoints and press **F5** again. Then select the dotnet process to attach to.
![](/3-start-debugging.gif)
6. In the Debug window, you can see the variables in the left panel.

[Azure IoT Edge extension](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-edge) also supports developing, debugging and deploying Azure Function for IoT Edge. For more information, please visit [here](https://aka.ms/DevelopeAzureFunctionOnEdge).

## Support and Contact us ##
You can join in our [Gitter](https://gitter.im/Microsoft/vscode-azure-iot-edge) to ask for help, report issues and talk to the product team directly.
