# Entorno de desarrollo ArduPilot en Linux

## Clonar el ropositorio de ArduPilot

    $ cd ~
    $ git clone https://github.com/ArduPilot/ardupilot.git
    $ cd ardupilot
    $ git submodule update --init --recursive

## Instalar dependencias

    $ cd ~/ardupilot/
    $ Tools/environment_install/install-prereqs-ubuntu.sh -y
    $ . ~/.profile

## Iniciar el simulador SITL

Para iniciar el simulador primero cambia de directorio `ardupilot`.

    $ cd ~/ardupilot

Para simular un muticopter cambia a la carpeta `ArduCopter`

    $ cd ArduCopter

Cuando ejecutes por primera vez el simulador usa el argumento `-w` para compilar una EEPROM virtual y cargarla con los parametros por defecto para el vehiculo.

    $ sim_vehicle.py -w

Una vez que el proceso de compilación anterior terminó termina el proceso usando `Ctrl+C`. Después de eso puedes iniciar el simulador normalmente usando el siguiente comando.

    $ sim_vehicle.py --console --map

Puedes ver las opciones de lanzamiento del simulador usando el parámetro `-h`.

    $ sim_vehicle.py -h
