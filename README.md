# Drone

The autonomous drone we have built can be operated through either a computer program or a remote controller. The drone can hold itself steady in the air even when the remote control is disabled, thus the name - autonomous. The program allows the user to set a predefined path of flight. The drone is capable of launching and landing, all on its own. It consists of a Pixhawk 4 flight controller as its prime component which includes an inbuilt gyroscope and an accelerometer. We have onboard GPS module and telemetry module for obtaining on-flight stats. With this, we hope to finally set foot into the exciting world of UAVs.
For now, the we have used open source codes avalable to build the drone. We have used the QGroundControl software. We plan to develop on it. The scope of application for such a drone can be expanded greatly, with the addition of proximity sensors, LiDAR or cameras of different sorts to sense its surroundings. The input from the sensors can be used to optimize the path of the drone using machine learning algorithms. We can also use slam algorithms and let it automatically determine an optimal path to its destination (avoiding the obstacles in its path).

# Components & Materials

- Holybro Pixhawk 4 (Controller)
- Holybro PM07 V2.4 (Power supply module)
- FrSKY RX8R Pro 2.4G ACCST 8/16CH SBUS Telemetry Recevier
- 3dr 500mW Radio Telemetry (Air & Ground modules)
- Emax Mt2213-935kv Brushless motors
- 45A Brushless ESC Module
- Propellers (1045)
- 3S LiPo Battery 11.1V
- Aluminum Box pipes (for arms)
- Sunmica (for chasis)
- Pixhawk 4 GPS module
- Rubber Spacers, nuts, bolts, wires, LED lights(optional)

# Working Idea

Using available senory modules, i.e. GPS, Accelerometer, Compass, to calculate optimal power input for the fan motors. While allowing for user input to change flight paramaters.

# Chasis

## Design

- Two 13x13 cm sunmica board (enacasing)
- 4 equal size aluminium box pipes
- 

# Circuit

![Screenshot 2023-09-28 203558](https://github.com/CodeScythe0/Drone/assets/115811767/f2d5933e-f747-4cd8-8f19-c0e8a2d6675e)
