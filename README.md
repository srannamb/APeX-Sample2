# APeX-Sample2
Sample code for an IoT gateway utilizing APeX HDK and APIs

## Objective

This sample code illustrates building an IoT gateway module utilizing the popular Raspberry Pi, an APeX hardware kit, and a Cisco Aironet AP 3800

### Prerequisites

(1) APeX HDK plugged into Cisco Aironet AP3800 module port (2) Aironet AP3800 connected to Wireless Lan Controller and a valid IP address (3) Raspberry Pi connected to the APeX HDK (power and ethernet) (4) Internet connectivity available on Raspberry Pi

Executing sample application

Open a shell terminal on Raspberry Pi and run the following commands:

``` sh
sudo apt-get install python-wxgtk3.0 python-matplotlib python-pip python-numpy

```

This will install a python based windowing toolkit, and a Python package manager (pip)

If you are using a DevNet Sandbox reservation instance, you can get instructions in the Learning Lab

You are now ready to execute the sample application.

Log into the shell terminal of your Raspberry Pi and execute the following command to download the latest sample code:
``` sh
git clone https://github.com/dbhatt/APeX-Sample2.git
cd APeX-Sample2
```
/// Execute the SensorSimulator.py script to simulate events from an IoT sensor. The sensor simulator simulates the following telemetry data:
(a) Temperature
(b) 3-axis accelerometer (motion)
(c) Pressure
You can turn on the sensor simulator with the following command:
``` sh
python SensorSimulator.py &
```
This script publishes the sensor events to an MQTT broker.

In order to receive these sensor events, push them to a cloud or run other analytics, open a new terminal and execute the following NodeJs script:
``` sh
node index.js
```
This script subscribes to the IoT sensor messages with the MQTT broker. As the sensor simulator script generates and publishes a sensor event, the subscriber (in this case the NodeJS client) receives the event and can be appropriately handled by the client.
