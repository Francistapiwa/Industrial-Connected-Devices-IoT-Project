# Constrained Device Application (Connected Devices)

## Lab Module 06

Be sure to implement all the PIOT-CDA-* issues (requirements) listed at [PIOT-INF-06-001 - Lab Module 06](https://github.com/orgs/programming-the-iot/projects/1#column-10488434).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Connection Management: Manages the connection to an MQTT broker, enabling communication with other devices or services.
Data Transmission: Publishes device data to a specified topic and subscribes to relevant topics to receive updates or commands.
Event Handling: Handles connection events and incoming messages using callback methods, providing real-time feedback and control.
Modularity: Allows for easy integration and reuse of the MQTT client functionality within the broader application architecture, such as a device management system.
How does your implementation work?
In summary, this implementation enables:

Real-Time Messaging: Devices can send and receive messages in real time over MQTT, a lightweight messaging protocol ideal for IoT applications.
Event-Driven Communication: Using callback methods, the implementation can react to events such as message reception and connection loss, allowing for responsive applications.
Modular Design: The separation of concerns allows the MQTT functionality to be easily reused and integrated into other systems, like DeviceDataManager.
### Code Repository and Branch

NOTE: Be sure to include the branch (e.g. https://github.com/programming-the-iot/python-components/tree/alpha001).

URL: 
https://github.com/Francistapiwa/python-components/tree/lab06
### UML Design Diagram(s)
![alt text](<uml lab06.png>)
NOTE: Include one or more UML designs representing your solution. It's expected each
diagram you provide will look similar to, but not the same as, its counterpart in the
book [Programming the IoT](https://learning.oreilly.com/library/view/programming-the-internet/9781492081401/).


### Unit Tests Executed

NOTE: TA's will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- MqttClientConnectorTest
- SystemPerfomanceManager
- Data IntegrationTest
- 

### Integration Tests Executed

NOTE: TA's will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- ConstrainedDeviceAppTest
- DeviceDataManagerNoCommsTest
- ActuatorAdapterManagerTest
- SensorAdapterManagerTest
- 
- 

EOF.
