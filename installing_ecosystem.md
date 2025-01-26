# Installation
### Installation for SITL Implementation
* Install Ardupilot and MAVProxy using these [instructions](https://github.com/Intelligent-Quads/iq_tutorials/blob/master/docs/Installing_Ardupilot_20_04.md).
* Install QGroundControl using these [instructions](https://github.com/Intelligent-Quads/iq_tutorials/blob/master/docs/installing_qgc.md).
* Install ROS  in the system and MAVROS in the catkin_ws using these [instructions](https://github.com/Intelligent-Quads/iq_tutorials/blob/master/docs/installing_ros_20_04.md).
* Clone the IQ_GNC Package in the catkin_ws using the following command
  ```
  git clone https://github.com/Intelligent-Quads/iq_gnc.git
  ```
* Replace the ***iq_gnc*** and ***iq_sim*** folders with the folders having the same name in the ***Packages/*** folder of the repository.
* Finally build the workspace by executing the `catkin_make` command in the catkin_ws folder.

### Install mavros
    ```
    sudo apt-get install ros-noetic-mavros ros-noetic-mavros-extras
    wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh
    chmod a+x install_geographiclib_datasets.sh
    ./install_geographiclib_datasets.sh
    ```

# Running simulations in SITL
* For launching runway.world, run
  ```
  roslaunch iq_sim runway.launch
  ```
* Launch the ardupilot instance by running
  ```
  cd ~/ardupilot/ArduCopter/ && sim_vehicle.py -v ArduCopter -f gazebo-iris --console
  ```
* Launch the connection to QGround control using the following command in different tab
  ```
  roslaunch iq_sim apm.launch
  ```
* Run the QGroundControl
* Run the drone_sense_avoid file using the command
  ```
  rosrun iq_sim drone_sense_avoid.py
  ```
