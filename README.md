[![Build][build-badge]][build-url]
[![Issues][issues-badge]][issues-url]
[![Gitter][gitter-badge]][gitter-url]

Azure IoT Device Simulation
=====================================
Note: As of May 6th 2021, the Device Simulation solution accelerator is no longer supported. This repository has been archived.

Overview
========

As IoT is growing, so is the need for technologies to help accelerate the development and testing of new and existing IoT solutions. Azure IoT Device Simulation helps you build simulated devices that look and behave like the real thing enabling powerful testing scenarios. With this project you can gather, process, analyze and act on data from simulated devices allowing you to test your solutions near end to end. You can evaluate how well your solution processes, manages, and presents the data being generated by your simulated devices.
Get up and running instantly by using sample devices and sample simulations when you care less about the actual data and just want to see data flowing through the system.

- Get a prototype up and running quickly and iterate at amazing speeds by adjusting simulated device behavior on the fly. Prove out the idea before investing in costly hardware. You can create custom devices through the UI to generate a prototype device in seconds.
- Validate the solution works as expected from device to solution by simulating real-world device behaviors. You can script complex device behaviors using JavaScript to ensure the most accurate simulated device telemetry possible.
- Build confidence in your solution by simulating both normal, peak, and beyond peak load conditions.
- Make Device Simulation your own by modifying our open source code to meet your specific needs. 

![Device Simulation Screen Shot](/docs/SimulationScreenShot.png)


Common Scenarios
================

1.	**Load Testing** – Customers will be able to perform large scale tests using Device Simulation. Individual simulations will support up to 20,000 simulated devices. 
2.	**IoT Demos** – Device Simulation now includes sample simulations that can be started with a click. This allows for instant demos showcasing device data flowing to an IoT Hub.
3.	**Simple POCs** – This scenario was supported in the initial release of Device Simulation. However, there are more capabilities here. Customers can create device models and re-use them for easily repeatable simulations. Individual simulations can also now support a mix of multiple device types.
4.	**Advanced device behaviors** – Customers will be able to write custom JSON device definition files and script device behaviors using JavaScript. This allows for very complex scenarios allowing a device to mimic the behavior of the real thing (e.g. vehicles following roads, interior temperature varying based on exterior temperature, etc.)
5.	**Simulation-driven development** – Customers can use Device Simulation to generate both expected and unexpected telemetry for continuous testing while developing their solution on top of Azure IoT.

Getting Started
===============
To get started with this project, deploy it to your Azure subscription. Follow the [deployment instructions](deployment/README.md) to get started.

Project Structure
=====================

The solution contains the following projects and folders:
-	**WebService:** ASP.NET Web API exposing a RESTful API for Simulation functionality, e.g. start, stop, add devices, etc. This is also the service entry point, starting all the main threads.

- **pcs-config-dotnet**  Configuration Library used to create and store configuration settings specific to your deployment
- **pcs-diagnostics-dotnet** Diagnostics Library used to Collect metrics on how the application is used and optionally send this data to Microsoft.
- **simulation-service** Microservice that manages all simulations
- **storage-service** Microservice that allows management of key-values abstracting the storage semantic and store data of any format using Azure CosmosDB
- **webui** The web user interface for Device Simulation. The service provides a RESTful endpoint to configure the simulation details, to start and stop the simulation, to add and remove virtual devices, and more.
- **deployment** Scripts to configure and deploy 

Other Resources
====================================

-	[Device Models specification](https://github.com/Azure/device-simulation-dotnet/wiki/Device-Models)
-	[Simulation service API specs](https://github.com/Azure/device-simulation-dotnet/wiki/%5BAPI-Specifications%5D-Service)
-	[Device Models API specs](https://github.com/Azure/device-simulation-dotnet/wiki/%5BAPI-Specifications%5D-Device-Models)
-	[Simulations API specs](https://github.com/Azure/device-simulation-dotnet/wiki/%5BAPI-Specifications%5D-Simulations)


Contributing
============
Refer to our [contribution guidelines](docs/CONTRIBUTING.md)

License
=======
Copyright (c) Microsoft Corporation. All rights reserved.

Licensed under the [MIT](LICENSE) License.

[build-badge]: https://img.shields.io/travis/Azure/azure-iot-pcs-simulation.svg
[build-url]: https://travis-ci.org/Azure/azure-iot-pcs-simulation
[issues-badge]: https://img.shields.io/github/issues/azure/azure-iot-pcs-simulation.svg
[issues-url]: https://github.com/azure/azure-iot-pcs-simulation/issues
[gitter-badge]: https://img.shields.io/gitter/room/azure/iot-solutions.js.svg
[gitter-url]: https://gitter.im/Azure/iot-solutions