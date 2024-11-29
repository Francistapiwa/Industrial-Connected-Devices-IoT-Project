# Gateway Device Application (Connected Devices)

## Lab Module 08

Be sure to implement all the PIOT-GDA-* issues (requirements) listed at [PIOT-INF-08-001 - Lab Module 08](https://github.com/orgs/programming-the-iot/projects/1#column-10488501).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
The implementation creates a CoAP server using the Californium-core and Scandium-core libraries, designed to handle various CoAP requests for IoT devices. The main component is the CoapServerGateway class, which manages the server and hosts resources. It supports adding resource handlers, which process specific CoAP requests like PUT, GET, etc., either internally or externally.

Three key resource handlers are defined:

UpdateSystemPerformanceResourceHandler: Handles PUT requests to update system performance data.
UpdateTelemetryResourceHandler: Handles PUT requests to update sensor telemetry data.
GetActuatorCommandResourceHandler: Handles CoAP OBSERVE requests for receiving actuation commands from the Global Data Aggregator (GDA).
These handlers are modeled after a base class, GenericCoapResourceHandler, which simplifies the creation of new handlers. The CoapServerGateway integrates with the DeviceDataManager, which manages device-specific data and can register an IActuatorDataListener. This listener is responsible for responding to actuator data events.

The entire system enables efficient, asynchronous CoAP-based communication, where devices can send updates, telemetry data, and actuation commands. The CoapServerGateway serves as a central hub for managing resources, while DeviceDataManager handles external data interactions and listens for actuator events. This setup is essential for scalable IoT applications.

How does your implementation work?
The implementation works by setting up a CoAP server using the Californium-core and Scandium-core libraries to enable communication between IoT devices and services. The main class, CoapServerGateway, manages the server, hosts resources, and processes CoAP requests. It can dynamically add resource handlers, which handle specific CoAP methods (e.g., GET, PUT).

Three resource handler classes are implemented:

UpdateSystemPerformanceResourceHandler: Handles PUT requests to update system performance data.
UpdateTelemetryResourceHandler: Handles PUT requests to update sensor telemetry data.
GetActuatorCommandResourceHandler: Handles CoAP OBSERVE requests to receive actuation commands.
These handlers are based on a template class, GenericCoapResourceHandler, simplifying the creation of new handlers for different data types. The CoapServerGateway integrates with the DeviceDataManager, which is responsible for managing devices and their data.

The DeviceDataManager supports the registration of an IActuatorDataListener, which listens for actuator data events. The server can either create resource handlers internally or receive them from the DeviceDataManager.

This setup allows efficient, asynchronous communication in an IoT system, where devices can send updates, telemetry, and actuation commands using the CoAP protocol. The CoapServerGateway serves as a central hub for managing resources, while the DeviceDataManager manages the external data interactions.

### Code Repository and Branch

NOTE: Be sure to include the branch (e.g. https://github.com/programming-the-iot/python-components/tree/alpha001).

URL: https://github.com/Francistapiwa/Java-components/tree/lab08

### UML Design Diagram(s)

NOTE: Include one or more UML designs representing your solution. It's expected each
diagram you provide will look similar to, but not the same as, its counterpart in the
book [Programming the IoT](https://learning.oreilly.com/library/view/programming-the-internet/9781492081401/).
![alt text](<uml 8 gda.png>)

### Unit Tests Executed

NOTE: TA's will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- ConfigUtilTest
- GatewayDeviceAppTest
- SystemPerformanceManagerTest
- SystemCpuUtilTaskTest
- ActuatorDataTest
- SensorDataTest
- SystemPerformanceDataTest
- SystemMemUtilTaskTest
- SystemStateDataTest
- DataUtilTest

### Integration Tests Executed

NOTE: TA's will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- GatewayDeviceAppTest
- DataIntegrationTest
- DeviceDataManagerNoCommsTest
- MqttClientConnectorTest
- CoapClientToServerConnectorTest

EOF.
