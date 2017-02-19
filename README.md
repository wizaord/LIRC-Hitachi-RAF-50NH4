# LIRC-Hitachi-RAF-50NH4
LIRC configuration for Hitachi RAR 50NH4

#Prerequis
Installer sur le poste LIRC avec les configurations suivantes
Pour faire marcher la 0.9.4.c

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



