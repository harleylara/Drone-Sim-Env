# Instalación de QGroundControl en Linux

## Instalar dependencias necesarias

    $ sudo usermod -a -G dialout $USER
    $ sudo apt-get remove modemmanager -y
    $ sudo apt install gstreamer1.0-plugins-bad gstreamer1.0-libav gstreamer1.0-gl -y

## Descargar e instalar QGroundControl

Para descargar el la ultima versión de QGroundControl puedes usar el siguiente comando.

    $ cd ~ && mkdir QGroundControl && cd QGroundControl && wget https://s3-us-west-2.amazonaws.com/qgroundcontrol/latest/QGroundControl.AppImage
    $ chmod +x ./QGroundControl.AppImage
    $ ./QGroundControl.AppImage

## Crear acceso directo

Además puedes crear una acceso directo en el escritorio copiando y pegando el archivo `QGroundControl.AppImage`.

    $ cp ~/QGroundControl/QGroundControl.AppImage ~/Desktop
