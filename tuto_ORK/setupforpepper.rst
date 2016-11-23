Setup ORK for Pepper
====================

Main web-page (regardless the robot):

http://wg-perception.github.io/object_recognition_core/ 

Installation
------------

* At first, try the easiest way, install with apt-get

    .. code-block:: bash
    
        sudo apt-get install ros-indigo-object-recognition-*

* Then, try to start it (go to the next section).

* If it does not work, then remove it 

    .. code-block:: bash
    
        sudo apt-get remove ros-indigo-object-recognition-*

and follow the installation from source 
http://wg-perception.github.io/object_recognition_core/install.html#install 


Launch
------

* Start pepper_bringup

    .. code-block:: bash
        
        export NAO_IP=10.0.205.244
        
        roslaunch pepper_bringup pepper_full.launch

* copy configuration files from the current git folder

* start ORK
  either Tabletop method

    .. code-block:: bash
    
        rosrun object_recognition_core detection -c /home/nlyubova/catkin_ork/src/tabletop/conf/detection.object_pepper_bringup.ros.ork

  or start Linemod method

    .. code-block:: bash

        rosrun object_recognition_core detection -c /home/nlyubova/catkin_ork/src/linemod/conf/detection.robot_pepper_naoqi.ros.ork

* start RviZ

    .. code-block:: bash
   
        rosrun rviz rviz
        
  ensure that you can get images from the following topics:
  
    * /naoqi_driver_node/camera/depth_registered/image_rect
    
    * /naoqi_driver_node/camera/front/image_rect_color
