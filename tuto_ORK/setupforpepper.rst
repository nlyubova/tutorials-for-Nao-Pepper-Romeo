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

Prepare the setup 

* download configuration files from this git and place them to linemod/conf and tabletop/conf

* download a coke mesh and add it in the DB, check `here <http://wg-perception.github.io/ork_tutorials/tutorial01/tutorial.html>`_

Prepare the robot

* Start pepper_bringup

    .. code-block:: bash
        
        export NAO_IP=10.0.205.244
        
        roslaunch pepper_bringup pepper_full.launch

* start RviZ

    .. code-block:: bash
   
        rosrun rviz rviz
        
  ensure that you can get images from the following topics:
  
    * /naoqi_driver_node/camera/depth_registered/image_rect
    
    * /naoqi_driver_node/camera/front/image_rect_color


To launch ORK Tabletop method

* start ORK Tabletop

    .. code-block:: bash
    
        rosrun object_recognition_core detection -c `rospack find object_recognition_tabletop`/conf/detection.tabletop_object_pepper_bringup.ros.ork

To launch ORK Linemod method

* train
  
    .. code-block:: bash

        rosrun object_recognition_core training -c `rospack find object_recognition_linemod`/conf/training.linemod_pepper.ork
        
* start recognition, either in a continuous mode
  
    .. code-block:: bash
    
        rosrun object_recognition_core detection -c `rospack find object_recognition_linemod`/conf/detection.linemod_pepper_bringup.ros.ork

* or start recognition in a client-server mode

    .. code-block:: bash
    
        rosrun object_recognition_ros server -c `rospack find object_recognition_linemod`/conf/detection.linemod_pepper_bringup.ros.ork

    .. code-block:: bash

        rosrun object_recognition_ros client
