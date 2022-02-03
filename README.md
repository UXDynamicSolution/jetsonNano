# jetsonNano
Apuntes de configuración y demases

# CONFIGURACIÓN DE VENTILADOR JETSON NANO

### Comando para ejecutar el ventilador, el parámetro 255 corresponde a la velocidad del ventilador, rango (0-255)
sudo sh -c 'echo 255 > /sys/devices/pwm-fan/target_pwm' 

### Modificando este archivo podemos iniciar el ventilador cuando iniciamos la placa Jetson Nano (vi, nano, etc):
sudo vi /etc/rc.local

### Creamos un script bash con el comando anterior:
#!/bin/bash

sleep 10

sudo /usr/bin/jetson_clocks

sudo sh -c 'echo 255 > /sys/devices/pwm-fan/target_pwm'


### Modificamos los permisos y además le damos permiso de ejecución:
sudo chmod u+x rc.local

### Reiniciamos la Jetson Nano para verificar:
sudo reboot

# INSTALAR requirements.txt

### Comando para instalar la lista de requisitos especificados ese archivo:

pip3 install -r requirements.txt

### numerar todos los paquetes pip instalados

pip3 list

### Entorno virtual
entorno virtual lo que hace es generar espacios de trabajo con distintos paquetes y dependencias. Esto principalmente nos evita que haya problemas entre paquetes y que tengamos de una forma más ordenada los distintos proyectos en los que estamos trabajando.

pip install --user pipenv







