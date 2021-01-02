# Instalación de MAVROS

Instale el paquete de mavros y mavros-extras para ROS Melodic

    $ sudo apt-get install ros-melodic-mavros ros-melodic-mavros-extras

Luego, instale los conjuntos de datos **GeographicLib** ejecutando el comando:

    $ cd ~
    $ wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh
    $ chmod +x install_geographiclib_datasets.sh
    $ sudo ./install_geographiclib_datasets.sh
    $ cd ~/catkin_ws
    $ catkin_make
