# Instalación de ROS Melodic

(En la máquina virtual)

Configura tu computadora para aceptar software proveniente de _packages.ros.org_.

    $ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

Agrega las claves.

    $ sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

Asegurate que el índice de paquetes Debian está actualizado.

    $ sudo apt-get update

Para instalar _ROS Desktop-Full_ (RECOMENDADO) ejecuta el siguiente comando, lo cual incluye: ROS, rqt, rviz, robot-generic libraries, simuladores 2D/3D, navegación y percepción 2D/3D.

    $ sudo apt-get install ros-melodic-desktop-full

Configuración del entorno.

    $ echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
    $ source ~/.bashrc
    $ source /opt/ros/melodic/setup.bash

Intalación de las dependencias para construir paquetes.

    $ sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential

Inicialización de rosdep.

    $ sudo apt install python-rosdep
    $ sudo rosdep init
    $ rosdep update

Listo! ahora tiene una máquina virtual con Linux Ubuntu y ROS instalado.

## Preparar el espacio de trabajo para paquetes ROS

    $ source /opt/ros/melodic/setup.bash
    $ mkdir -p ~/catkin_ws/src
    $ cd ~/catkin_ws/
    $ catkin_make
    $ source devel/setup.bash
