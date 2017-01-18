ROS tutorials for Nao, Pepper, Romeo robots
===========================================

Here, we describe the main steps to setup your system and use ROS Kinetic with Nao, Pepper, or Romeo. We provide examples of installing all packages with "apt-get" if possible, however each package can be also installed from source (check the corresponding Github links).  

Pre-requirements
----------------

* installed Ubuntu, check http://howtoubuntu.org/how-to-install-ubuntu-14-04-trusty-tahr

* installed ROS (Indigo for Ubuntu 14 or Kinetic for Ubuntu 16), check http://wiki.ros.org/Installation

  .. code-block:: bash

        sudo apt-get install ros-kinetic-desktop
        source /opt/ros/kinetic/setup.bash

Installation
------------

* if you use Nao robot, check http://wiki.ros.org/nao 

    * install basic packages
 
      .. code-block:: bash

            sudo apt-get install ros-kinetic-nao-robot ros-kinetic-nao-meshes

    * install MoveIt!-specific packages, check https://github.com/ros-naoqi/nao_moveit_config

      .. code-block:: bash

            sudo apt-get install ros-kinetic-moveit ros-kinetic-moveit-visual-tools

        * compile the following packages from source

          .. code-block:: bash

                mkdir -p ~/catkin_ws/src
                cd ~/catkin_ws/src
                git clone https://github.com/ros-naoqi/nao_moveit_config
                git clone https://github.com/ros-naoqi/nao_virtual
                git clone https://github.com/ros-naoqi/nao_dcm_robot
                cd ..
                catkin_make

    *  optionally, install Gazebo, check `the official tutorial <http://gazebosim.org/tutorials?tut=install_ubuntu>`_ and then `our tutorial <https://github.com/ros-naoqi/nao_virtual/tree/master/nao_gazebo_plugin>`_


* if you use any other robot, install all packages for -pepper- or -romeo- instead as -nao-

    * for Pepper, check http://wiki.ros.org/pepper
     
    * for Romeo, check http://wiki.ros.org/romeo



Testing
-------

*  source your ROS installation; 

  .. code-block:: bash

        source /opt/ros/kinetic/setup.bash
        source ~/catkin_ws/devel/setup.bash

*   launch MoveIt! and check if you see a robot, check the `tutorial <https://github.com/ros-naoqi/nao_moveit_config>`_

  .. code-block:: bash

        roslaunch nao_moveit_config demo.launch

*   optionally, if you have installed Gazebo, then check it and see the `tutorial <https://github.com/ros-naoqi/nao_virtual/tree/master/nao_gazebo_plugin>`_

  .. code-block:: bash

        roslaunch nao_gazebo_plugin nao_gazebo_plugin_H25.launch



Please, open PR if you find any typos :) or question, and I will try to help you.
