ROS tutorials for Nao, Pepper, Romeo robots
===========================================

Here, we describe the main steps to setup your system and use ROS with Nao, Pepper, or Romeo. We provide examples of installing all packages with "apt-get" if possible, however each package can be also installed from source (check the corresponding Github links).  

Pre-requirements
----------------

* install Ubuntu (14.04 is the supported one and earlier versions are possible), check http://howtoubuntu.org/how-to-install-ubuntu-14-04-trusty-tahr

* install ROS (Indigo for Ubuntu 14 or Kinetic for Ubuntu 16), check http://wiki.ros.org/Installation

    .. code-block:: bash

        sudo apt-get install ros-<ROS_version>-desktop
   
* install MoveIt!, check http://moveit.ros.org/

    .. code-block:: bash
    
        sudo apt-get install ros-<ROS_version>-moveit

* source your installation

    .. code-block:: bash

        source /opt/ros/<ROS_version>/setup.bash

Installation
------------

* if you use Nao robot, check http://wiki.ros.org/nao and install the following packages replacing <ROBOT> by nao 

    * install basic packages

    .. code-block:: bash

          sudo apt-get install ros-<ROS_version>-<ROBOT>-robot ros-<ROS_version>-<ROBOT>-meshes

    * install MoveIt!-specific packages, check https://github.com/ros-naoqi/nao_moveit_config

    .. code-block:: bash

          sudo apt-get install ros-<ROS_version>-moveit-visual-tools ros-<ROS_version>-<ROBOT>-moveit-config

    *  optionally, install Gazebo, check `the official tutorial <http://gazebosim.org/tutorials?tut=install_ubuntu>`_ and then `our tutorial <https://github.com/ros-naoqi/nao_virtual/tree/master/nao_gazebo_plugin>`_

    .. code-block:: bash

          sudo apt-get install ros-<ROS_version>-<ROBOT>-control ros-<ROS_version>-<ROBOT>-gazebo-plugin


* if you use any other robot, additionally install all packages for <pepper> or <romeo> instead as <ROBOT>

    * if you use Pepper, check http://wiki.ros.org/pepper

    .. code-block:: bash

          sudo apt-get install ros-<ROS_version>-pepper-robot ros-<ROS_version>-pepper-meshes
          sudo apt-get install ros-<ROS_version>-pepper-moveit-config
          sudo apt-get install ros-<ROS_version>-pepper-control ros-<ROS_version>-pepper-gazebo-plugin
      
    * if you use Romeo, check http://wiki.ros.org/romeo

    .. code-block:: bash

          sudo apt-get install ros-<ROS_version>-romeo-robot
          sudo apt-get install ros-<ROS_version>-romeo-moveit-config
          sudo apt-get install ros-<ROS_version>-romeo-control ros-<ROS_version>-romeo-gazebo-plugin


Testing
-------

*  source your ROS installation; 
    * in case of installing everything with "apt-get", do

    .. code-block:: bash

        source /opt/ros/<ROS_version>/setup.bash

    * in case of installing from source, source your catkin workspace, for example

    .. code-block:: bash

        source ~/catkin_ws/devel/setup.bash

*   launch MoveIt! and check if you see a robot, check the `tutorial <https://github.com/ros-naoqi/nao_moveit_config>`_

.. code-block:: bash

    roslaunch nao_moveit_config demo.launch

*   optionally, if you have installed Gazebo, check the `tutorial <https://github.com/ros-naoqi/nao_virtual/tree/master/nao_gazebo_plugin>`_

.. code-block:: bash

    roslaunch nao_gazebo_plugin nao_gazebo_plugin_H25.launch



Please, open PR if you find any typos :) or question, and I will try to help you.
