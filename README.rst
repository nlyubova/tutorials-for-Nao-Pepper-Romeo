ROS tutorials for Nao, Pepper, Romeo robots
===========================================

Here we describe the main steps to setup your system and use ROS with Nao, Pepper, Romeo. We provide examples of installing all packages with "apt-get", however each package can be also installed from source (check the corresponding Github links).  

* install Ubuntu (14.04 is fine, others are possible), check http://howtoubuntu.org/how-to-install-ubuntu-14-04-trusty-tahr

* install ROS (Indigo is recommended), check http://wiki.ros.org/Installation

    .. code-block:: bash

        sudo apt-get install ros-indigo-desktop
        source /opt/ros/indigo/setup.bash
    
* if you use Nao (recommended), check http://wiki.ros.org/nao

    .. code-block:: bash

          sudo apt-get install ros-indigo-nao-robot ros-indigo-nao-meshes

    * install MoveIt!, check https://github.com/ros-naoqi/nao_moveit_config

    .. code-block:: bash

          sudo apt-get install ros-indigo-moveit-full ros-indigo-moveit-visual-tools ros-indigo-nao-moveit-config

    *  optionally, install Gazebo, check https://github.com/ros-naoqi/nao_virtual/tree/master/nao_gazebo_plugin

    .. code-block:: bash

          sudo apt-get install ros-indigo-nao-control ros-indigo-nao-gazebo-plugin


* if you use any other robot, additionally install all packages for <pepper> or <romeo> instead of <nao>

* if you use Pepper, check http://wiki.ros.org/pepper

    .. code-block:: bash

          sudo apt-get install ros-indigo-pepper-robot ros-indigo-pepper-meshes
          sudo apt-get install ros-indigo-pepper-moveit-config
          sudo apt-get install ros-indigo-pepper-control ros-indigo-pepper-gazebo-plugin
      
* if you use Romeo, check http://wiki.ros.org/romeo

    .. code-block:: bash

          sudo apt-get install ros-indigo-romeo-robot
          sudo apt-get install ros-indigo-romeo-moveit-config


Test your setup:

*  source your ROS installation; in case of installing everything with "apt-get", do

.. code-block:: bash

    source /opt/ros/indigo/setup.bash

*   Launch MoveIt!, check the tutorial https://github.com/ros-naoqi/nao_moveit_config

.. code-block:: bash

    roslaunch nao_moveit_config demo.launch

*   Launch Gazebo, check the tutorial https://github.com/ros-naoqi/nao_virtual/tree/master/nao_gazebo_plugin

.. code-block:: bash

    roslaunch nao_gazebo_plugin nao_gazebo_plugin_H25.launch



Please, let me know if you find any typos :) or any question, and I will try to help you.
