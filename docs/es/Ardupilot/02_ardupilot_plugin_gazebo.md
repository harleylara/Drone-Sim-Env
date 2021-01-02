# Gazebo y Ardupilot STIL

## Dependencias para el plugin Ardupilot

    $ cd ~
    $ sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'
    $ wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
    $ sudo apt update

Es necesario instalar una libreria de desarrollo para poder compilar el plugin en Gazebo 9

    $ sudo apt-get install libgazebo9-dev

Compilar el plugin:

    $ git clone https://github.com/SwiftGust/ardupilot_gazebo
    $ cd ardupilot_gazebo
    $ mkdir build
    $ cd build
    $ cmake ..
    $ make -j4
    $ sudo make install

    $ echo 'source /usr/share/gazebo/setup.sh' >> ~/.bashrc

Configurar la ruta de los modelos y mundos

    $ echo 'export GAZEBO_MODEL_PATH=~/ardupilot_gazebo/models:${GAZEBO_MODEL_PATH}' >> ~/.bashrc
    $ echo 'export GAZEBO_MODEL_PATH=~/ardupilot_gazebo/models_gazebo:${GAZEBO_MODEL_PATH}' >> ~/.bashrc
    $ echo 'export GAZEBO_RESOURCE_PATH=~/ardupilot_gazebo/worlds:${GAZEBO_RESOURCE_PATH}' >> ~/.bashrc
    $ echo 'export GAZEBO_PLUGIN_PATH=~/ardupilot_gazebo/build:${GAZEBO_PLUGIN_PATH}' >> ~/.bashrc
    $ source ~/.bashrc

## Test

Ejecutar gazebo.

    $ gazebo --verbose iris_ardupilot.world

Si tienes un error al ejecutar el comando anterior puedes solucionarlo actualizando lo siguiente.

    $ sudo apt upgrade libignition-math2

En otra terminal ejecutar SITL.

    $ cd ~/ardupilot/ArduCopter/
    $ sim_vehicle.py -v ArduCopter -f gazebo-iris -m --mav10 --map --console -I0

En otra terminal ejecutar MAVROS.

    roslaunch mavros apm.launch fcu_url:=udp://127.0.0.1:14550@
