# Instalación de base de datos de modelos para Gazebo

    $ mkdir ~/gazebo_ws && cd ~/gazebo_ws
    $ git clone https://github.com/osrf/gazebo_models
    $ echo 'export GAZEBO_MODEL_PATH=~/gazebo_ws/gazebo_models:${GAZEBO_RESOURCE_PATH}' >> ~/.bashrc
    $ source ~/.bashrc
