# Constrained Device Application (Connected Devices)

## Lab Module 08

Be sure to implement all the PIOT-CDA-* issues (requirements) listed at [PIOT-INF-08-001 - Lab Module 08](https://github.com/orgs/programming-the-iot/projects/1#column-10488501).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
The implementation involves creating a Python CoAP server using two libraries: CoAPthon3 and aiocoap. The core class, CoapServerAdapter, manages the CoAP server and hosts IoT resources, allowing for the integration of resource handlers either internally or externally (e.g., from DeviceDataManager). The UpdateActuatorResourceHandler class handles PUT requests to update actuator states, enabling the Global Data Aggregator (GDA) to notify the Central Device Adapter (CDA) of new actuation events. The server is flexible, supporting dynamic resource handling, and uses CoAP to facilitate communication between IoT devices and services. This setup allows efficient, asynchronous interaction within IoT systems.

How does your implementation work?
The implementation creates a CoAP server in Python using two libraries: CoAPthon3 and aiocoap, which are both designed to handle IoT communications via the Constrained Application Protocol (CoAP). The main component is the CoapServerAdapter class, which manages the CoAP server and its resources. It supports adding resource handlers that respond to specific CoAP requests (like GET, PUT, POST, DELETE). These handlers can be created internally or passed in from external sources, such as DeviceDataManager.

The UpdateActuatorResourceHandler class is responsible for handling PUT requests that update the state of actuators within the IoT system. When the Global Data Aggregator (GDA) needs to notify the Central Device Adapter (CDA) of an actuation event, it sends actuator data via a PUT request. The server, configured with CoAPthon3 or aiocoap, handles asynchronous communication and updates across the IoT network.

This setup provides a flexible, scalable solution for managing IoT resources and handling actuation events in an efficient manner.




### Code Repository and Branch

NOTE: Be sure to include the branch (e.g. https://github.com/programming-the-iot/python-components/tree/alpha001).

URL: 

### UML Design Diagram(s)

NOTE: Include one or more UML designs representing your solution. It's expected each
diagram you provide will look similar to, but not the same as, its counterpart in the
book [Programming the IoT](https://learning.oreilly.com/library/view/programming-the-internet/9781492081401/).
![alt text](<lab 8 cda.png>)

### Unit Tests Executed

NOTE: TA's will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- ConfigUtilTest
- SystemCpuUtilTaskTest.
- SystemMemUtilTaskTest
- ActuatorDataTest
- SensorDataTest
- SystemPerformanceDataTest
- HumidifierActuatorSimTaskTest
- HvacActuatorSimTaskTest

### Integration Tests Executed

NOTE: TA's will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- ConstrainedDeviceAppTest
- SystemPerformanceManagerTest
- SensorAdapterManagerTest
- SensorAdapterManagerTest
- HumidityEmulatorTaskTest
- PressureEmulatorTaskTest
- TemperatureEmulatorTaskTest
- SenseHatEmulatorQuickTest
- EmbeddedSensorAdapterTest
- MqttClientConnectorTest
- CoapClientToServerConnectorTest

EOF.
