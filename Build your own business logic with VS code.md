# Build Your Own Business Logic for Azure IoT Edge with VS Code #
In Nov 2017, we're shipping [Azure IoT Edge](https://azure.microsoft.com/en-us/services/iot-edge/) preview version. [Azure IoT Edge](https://azure.microsoft.com/en-us/services/iot-edge/) is an Internet of Things (IoT) service that builds on top of IoT Hub. This service is meant for customers who want to analyze data on devices, a.k.a. "at the edge", instead of in the cloud. By moving parts of your workload to the edge, your devices can spend less time sending messages to the cloud and react more quickly to changes in status.

Along with this release, we have published [Azure IoT Edge extension](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-edge) and updated [Azure IoT Toolkit extension](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-toolkit) as well, to make it easy to code, build, deploy and debug your IoT Edge solutions in Visual Studio Code, by providing a rich set of functionalities:
* Create new IoT Edge projects
* Build and publish IoT Edge modules
* Debug IoT Edge modules locally
* Manage IoT Edge devices in IoT Hub
* Deploy IoT solutions to IoT Edge devices
* Stop and restart IoT Edge

![](/IoTEdgeExt.png)
## Get Started with IoT Edge in VS Code ##
### Create Edge Device ###
You can deploy Azure IoT Edge on a simulated device. Here are the tutorials for [Windows](https://docs.microsoft.com/en-us/azure/iot-edge/tutorial-simulate-device-windows) and [Linux](https://docs.microsoft.com/en-us/azure/iot-edge/tutorial-simulate-device-linux).
### Develop and deploy a C# IoT Edge module ###
You can create a new IoT Edge module and build your own business logic inside. Please follow [this tutorial](https://docs.microsoft.com/en-us/azure/iot-edge/tutorial-csharp-module) for more details.
### Debug your IoT Edge C# module ###
1. To start debugging, you need to use the dockerfile.debug to rebuild your docker image and deploy your Edge solution again. In VS Code explorer, select Dockerfile.debug and Right-click to choose Build IoT Edge module Docker image. Then containerize and publish your module image as usual. It's recommended to use a local registry to host your images for debugging purpose if you are working on Linux container.
![](/dockImageDebug.png)
2. You can reuse the deployment.json file if you have correct modules and routes for your IoT Edge. In command Palette (Ctrl+Shift+P), type and select Edge: Restart Edge to get your module started in debug version.
3. Configure your launch.json file:


	- If you don't have a launch.json file yet, go to VS Code debug window, press F5 and select IoT Edge (.Net Core). launch.json file will be generated for you.
	![](/1-add-config-new-launch-json.gif)
	- If launch.json file is already there, open it in VS Code, click "Add Configuration...", and select "Edge: Debug IoT Edge Module (.NET Core)"
	![](/1-add-config-existing-launch-json.gif)
4. In launch.json, navigate to Debug IoT Edge Module (.NET Core) section and specify the <container_name\>.
![](/2-update-container-name.gif)
5. Navigate to Program.cs. Add breakpoints and press F5 again. Then select the dotnet process to attach to.
![](/3-start-debugging.gif)
6. In Debug window, you can see the variables in the left panel.

[Azure IoT Edge extension](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-edge) also supports developing, debugging and deploying Azure Function for IoT Edge. For more info, please visit [here](https://aka.ms/DevelopeAzureFunctionOnEdge).

## Support and Contact us ##
You can join in our [Gitter](https://gitter.im/Microsoft/vscode-azure-iot-edge) to ask for help, report issues and talk to the product team directly.
