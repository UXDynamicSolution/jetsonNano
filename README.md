# jetsonNano
Apuntes de configuración y demases

1° Configuración de ventilador Jetson Nano al arranque. 

############## CONFIGURACIÓN DE VENTILADOR ########################
Comando para ejecutar el ventilador, el parámetro 255 corresponde a la velocidad del ventilador, rango (0-255)
sudo sh -c 'echo 255 > /sys/devices/pwm-fan/target_pwm' 

Modificando este archivo podemos iniciar el ventilador cuando iniciamos la placa Jetson Nano (vi, nano, etc):
sudo vi /etc/rc.local

Creamos un script bash con el comando anterior:
#!/bin/bash
sleep 10
sudo /usr/bin/jetson_clocks
sudo sh -c 'echo 255 > /sys/devices/pwm-fan/target_pwm'

Modificamos los permisos y además le damos permiso de ejecución:
sudo chmod u+x rc.local

Reiniciamos la Jetson Nano para verificar:
sudo reboot





