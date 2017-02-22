# LIRC-Hitachi-RAF-50NH4
LIRC configuration for Hitachi RAR 50NH4

#Prerequis
Installer sur le poste LIRC avec les configurations suivantes
Pour faire marcher la 0.9.4.c

L'idée va être de brancher l'emetteur RPI sur les gpio suivants :
*gpio 23 : pour l'emission de données
*gpio 22 : pour la réception de données (si vous voulez brancher un recepteur)

* Dans /boot/config.txt
```
# Uncomment this to enable the lirc-rpi module
dtoverlay=lirc-rpi,gpio_in_pin=23,gpio_out_pin=22
```

* Dans /etc/modules
```
lirc_dev
lirc_rpi gpio_in_pin=23 gpio_out_pin=22
```

#Pour capturer des trames
## couper le service
```bash
sudo service lircd stop
```

##capturer les trames
```bash
mode2 -m -d /dev/lirc0 > FICHIER.conf
```

#Pour lancer une commande
```
irsend SEND_ONCE HITACHIFORCE XXXX
ou XXX est le nom d'un bouton
```

# Le branchement sur Raspberry
## Raspberry pi 3
[Schema GPIO](./img/RPI3_gpio.png)

## Raspberry pi 1
[Schema GPIO](./img/RPI1_gpio.png)




