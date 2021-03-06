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
* `sudo apt install ros-galactic-joy-linux` Changed joy to joy_linux for controller support in raptor.

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
    
### Notes:
* `ls /opt/ros/galactic/include/` contains all packages installed into the ros distro.
* Download package directly into ros distro `sudo apt install ros-$ROS_DISTRO-<package-name>`
* `setup.<ext>`: first invokes the local_setup.<ext>
* `ls /lib/modules` Will list out the linux kernels present on your machine.
* `sudo apt install ros-$ROS_DISTRO-<package-name>`
* `package.xml` file contains a set of dependencies. The dependencies in this file are generally referred to as “rosdep keys”
 
* `uname -r` : Find Linux kernel version
 * It is common to have multiple kerneles present on your machine in case one breaks you can revert to an older kernel.
* (DKMS) Dynamic Kernel Module Support is a program/framework that enables generating Linux kernel modules whose sources generally reside outside the kernel source tree.
* Personal Package Archives (PPAs) are software repositories designed for Ubuntu users and are easier to install than other third-party repositories.
* /etc/apt/sources.list.d directory is as follows: Using the directory you can easily add new repositories without the need to edit the central /etc/apt/sources.list file.
