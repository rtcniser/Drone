# Drone

The autonomous drone we have built can be operated through either a computer program or a remote controller. The drone can hold itself steady in the air even when the remote control is disabled, thus the name - autonomous. The program allows the user to set a predefined path of flight. The drone is capable of launching and landing, all on its own. It consists of a Pixhawk 4 flight controller as its prime component which includes an inbuilt gyroscope and an accelerometer. We have onboard GPS module and telemetry module for obtaining on-flight stats. With this, we hope to finally set foot into the exciting world of UAVs.
For now, the we have used open source codes avalable to build the drone. We have used the QGroundControl software. We plan to develop on it. The scope of application for such a drone can be expanded greatly, with the addition of proximity sensors, LiDAR or cameras of different sorts to sense its surroundings. The input from the sensors can be used to optimize the path of the drone using machine learning algorithms. We can also use slam algorithms and let it automatically determine an optimal path to its destination (avoiding the obstacles in its path).

# Components & Materials

- Holybro Pixhawk 4 (Controller)
- Holybro PM07 V2.4 (Power supply module)
- Pixhawk 4 GPS module
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

The working principle of a drone involves the interaction of various components. The flight controller, which is the "brain" of the drone, receives control signals from the human or flight computer and sends control signals to the motor to execute. The Pixhawk 4 is a flight controller that turns control signals sent by the human or flight computer into a control signal for the motor to execute. It also helps with the stability of the drone with its onboard sensor arrays, which include an accelerometer and compass. The accelerometer measures the linear acceleration in 3D and determines the tilt angle of the drone in a stationary position. It also helps drones to detect obstacles in their environment and allows them to maintain a stable hover and navigate their environment. The compass helps the drone to maintain its heading.

A 12V LiPo battery is connected to the power module. The Holybro PM07 Pixhawk 4 Power Module supplies regulated 5.2V to the flight controller from the battery and provides current consumption and battery voltage measurements via analog signal through a 6 Pin JST-GH cable, along with integrated ESC power and signal distribution for up to 8 ESCs. The 4 brushless motors are connected to the power module via ESC modules, which is connected with the Pixhawk 4 with I/O communication.

The GPS module, FPV radio receiver, and telemetry module are connected to the Pixhawk 4. Pixhawk 4 connected with the GPS module send real time GPS data to the flight computer (ground control). The FPV radio reciever facilitates the communication between the drone and the remote control. The telemetry module facilitates the communication between the drone and the flight computer which requires a software "QGroundControl".

![Image](https://github.com/Sandipan04/Drone/blob/main/Screenshot_20231113_194938.png?raw=true)

## Flight Modes:

The pixhawk 4 flight controller provides different flight modes. Checkout the link for details: [PX4 Flight Modes](https://docs.px4.io/main/en/flight_modes/)

Generally, we use the Position, Hold and Altitude flight modes.

Caution: The Manual flight mode relies fully on the radio control. It does not hold its position or altitude. So, if you are using this mode, do it on your own responsibility.

## PID

PID stands for Proportional-Integral-Derivative, and it is a control algorithm used in drones to stabilize and control their movements. The PID controller continuously calculates an error value as the difference between a desired setpoint and a measured process variable and applies a correction based on proportional, integral, and derivative terms. The proportional term (P) looks at the present error, the integral term (I) looks at the past error, and the derivative term (D) looks at the future error. The PID controller's primary goal in a drone is to correct the error by adjusting motor speeds. The control loop continuously reads sensor data and calculates motor speeds to minimize the error. The PID algorithm is a crucial part of the control system, and it helps to stabilize the drone and make it more responsive to user input. The gains of a PID controller can be obtained by trial and error method. PID tuning is essential to achieve stability of the drone.

# Chasis Design

To make the body of the drone lighter in order to make it capable of lifting heavier payloads, we have used the following materials:
- Two 13x13 cm sunmica board (enacasing)
- Four equal size aluminium box pipes
- Four 3D-printed legs (for takeoff and landing)
- One 3D-printed GPS stand
- Two velcro (for holding battery)
- Some zip-ties (for wire management)

# Circuit

![Screenshot 2023-09-28 203558](https://github.com/CodeScythe0/Drone/assets/115811767/f2d5933e-f747-4cd8-8f19-c0e8a2d6675e)

# Softwares Used

- QGroundControl
  
  It helps in doing all the software related configurations of the drone, which otherwise would have to be done manually.

## Steps for configuration

- Connect the pixhawk 4 with computer (where QGroundControl is installed) and open the QgroundControl application.
- Go to vehicle setup, update/load firmware: PX4 flight stack.
- For Airframe, here, we have selected the Generic Quadcopter. You may select according to your drone design.
- Calibrate the radio and other sensor (Detailed instructions on how to calibrate are provided within the app).
- Check if all the motors are working properly from Vehicle setup > Motors.

Default/Current Channel setup (available under Vehicle setup > Flight modes):
+ Channel 1: Left/Right motion
+ Channel 2: Forward/Backward motion
+ Channel 3: Thrust
+ Channel 4: Rotation
+ Channel 5: Kill switch
+ Channel 6: Flight Arm switch
+ Channel 7: Return switch
+ Channel 8: Disengaged: Flight mode 1 (Position)
             Engaged: Flight mode 6 (Hold)

[QGroundControl User Guide](https://docs.qgroundcontrol.com/master/en/)
[Pixhawk 4 User Guide](https://docs.px4.io/main/en/hardware/drone_parts.html)
