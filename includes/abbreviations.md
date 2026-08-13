*[ROS2]: Robot Operating System 2, the framework that TidalCore is built on top of
*[TidalCore]: Built on ROS2, the software running directly on the boat
*[TidalShore]: Built using web technologies, the website which displays telemetry to remote operators
*[TidalView]: Built using Flutter, the driver dashboard deployed directly on the boat
*[ROSBridge]: Converts ROS2 messages into normal JSON which is used by TidalView
*[CAN]: Controller Area Network, the communication standard used by the motor controllers, BMS, and cooling sensors
*[CANOpen]: A standard built on top of CAN for more complex messaging using SDO's/PDO's/etc.
*[BMS]: Battery Management System; manages main battery charging, health, and sensor information
*[Kvaser]: The USB-to-CAN adapter used by TidalCore 
*[SDO]: Service Data Object; the primary method to get data from the motor controller
*[object dictionary]: A file which describes all the avaliable parameters from a CANOpen device