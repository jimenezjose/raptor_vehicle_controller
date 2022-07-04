# raptor_vehicle_controller
Control the New Eagle Raptor ECU using a game controller.

### Orgaization:
* Raptor
* Linux set up with ROS2
* CAN commincation between linux computer and raptor
* USB to CAN KVASER peripheral is used to send CAN messages to Raptor
* Joystick input recieved with the help of ROS2 joystick drivers.
* Using an Xbox One wired controller.
* Ubuntu 20.04
* Galactic
* Jetson Nano

### Main objective:
Write a ROS2 node that subscribes to a joystick data topic and transforms that data as Raptor messages sent through CAN.

* Receive Joystick data and publish it to a topic. (problem solved using [ROS2 generic joytsick driver](https://github.com/ros-drivers/joystick_drivers/tree/ros2)).
* Define/implement interface for ROS2 to Raptor CAN communication. (problem solved using [ROS2 Raptor driver](https://github.com/NewEagleRaptor/raptor-dbw-ros))

### Development:
* Run Raptor Joystick demo.
  * Install [ROS2 Kvaser interface](https://github.com/astuff/kvaser_interface/tree/ros2_master)
  * On the Jetson Nano there are two Kernels installed (5.4.0-121-generic, 4.9.253-tegra).
    * The tegra version is used on the host machine. The generic version is a backup. (`uname -r` : Find Linux kernel version`)
    * If you are getting issues on a backup kernel it should be fine if the kvaser software correctly gets installed on actual kernel.
    
