# raptor_vehicle_controller
Control the New Eagle Raptor ECU using a game controller.

Orgaization:
* Raptor
* Linux set up with ROS2
* CAN commincation between linux computer and raptor
* USB to CAN KVASER peripheral is used to send CAN messages to Raptor
* Joystick input recieved with the help of ROS2 joystick drivers.
* Using an Xbox One wired controller.
* Ubuntu 20.04
* Galactic

Main objective:
Write a ROS2 node that subscribes to a joystick data topic and transforms that data as Raptor messages sent through CAN.

Joystick data will be published to a `\joy` topic. (problem solved using ROS2 generic joytsick driver).
Raptor interface to receive CAN messages. (problem solved using ROS2 raptor driver).
