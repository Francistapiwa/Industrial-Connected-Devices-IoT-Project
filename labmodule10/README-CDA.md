# Constrained Device Application (Connected Devices)

## Lab Module 10

Be sure to implement all the PIOT-CDA-* issues (requirements) listed at [PIOT-INF-10-001 - Lab Module 10](https://github.com/orgs/programming-the-iot/projects/1#column-10488510).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Secure Communication: The MQTT connection is updated to support TLS encryption, ensuring secure data transmission.
Actuator Data Handling: The system is updated to handle actuator commands from the GDA, allowing control over actuators like temperature regulators.
Data Subscription: The MqttClientConnector subscribes to ActuatorData topics to receive commands and forward them to the appropriate listeners for processing.
Sensor Data Management: The DeviceDataManager collects sensor data (such as temperature) and sends it to the GDA.
Threshold-based Actuation: Temperature data is compared to configured thresholds, and if they are crossed, an actuation event is triggered to adjust the temperature (e.g., through a simulated heater or cooler).
In essence, this implementation ensures that:

Devices can securely communicate with each other and the cloud via TLS-encrypted MQTT.
Actuator commands are handled properly, allowing for real-time device control.
Sensor data is monitored, and actions like temperature adjustments are triggered based on predefined thresholds
How does your implementation work?
Secure TLS Encryption: Ensures that all communication (both data and commands) is encrypted and secure between devices and the cloud using MQTT.
Actuator Data Handling: The system listens for actuator commands from the GDA and processes them (e.g., turning on/off actuators).
Sensor Data Transmission: The system collects sensor data (like temperature readings) and sends it to the GDA using MQTT or CoAP.
Threshold Monitoring: If the temperature (or other sensor data) crosses configured thresholds (floor or ceiling), the system triggers an actuation event to adjust the environment (e.g., heating/cooling).
End-to-End Data Flow: The entire system works together to collect, transmit, and act on sensor data, while ensuring secure communication through TLS-encrypted MQTT.
### Code Repository and Branch

NOTE: Be sure to include the branch (e.g. https://github.com/programming-the-iot/python-components/tree/alpha001).

URL: 

### UML Design Diagram(s)
![alt text](<lab 10 cda.png>)
NOTE: Include one or more UML designs representing your solution. It's expected each
diagram you provide will look similar to, but not the same as, its counterpart in the
book [Programming the IoT](https://learning.oreilly.com/library/view/programming-the-internet/9781492081401/).


### Unit Tests Executed

NOTE: TA's will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

-ConfigUtilTest
- SystemCpuUtilTaskTest.
- SystemMemUtilTaskTest
- ActuatorDataTest
- SensorDataTest
- SystemPerformanceDataTest
- HumidifierActuatorSimTaskTest
- HvacActuatorSimTaskTest 
- 
- 

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

- 
- 

EOF.
