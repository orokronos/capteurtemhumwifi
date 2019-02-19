# CAPTEUR HUMIDITE TEMPERATURE WIFI(ESP3221)
le montage suivant va permettre de recuper les données de temperature et d'humidité
d'un capteur DHT11 connecté à un arduino wifi esp3221 les donnée passerons par un serveur mqtt geré
par le pc et l'on recevra les données sous forme de jauge via Node-Red.

## Liste des composants
+ 1 arduino ESP3221
+ 1 Capteur DHT11
+ 3 fils male/femelle
+ 1 breadboard
+ 1 cable micro usb

## CAPTEUR DHT11
![imagedht11](https://gloimg.gbtcdn.com/soa/gb/2015/201509/goods_img_big-v1/1441410570492-P-3065832.jpg)

## ARDUINO ESP3221 
![imageESP3221](https://cdn.instructables.com/FT7/FJUS/J7AQPOHS/FT7FJUSJ7AQPOHS.LARGE.jpg)

## MASTERIEL NECESSAIRE
+ un pc  wifi sous ubuntu avec serveur MOSCA (MQTT)installé et un serveur Node-Red


#  C EST PARTI MON AMI

D'abord je cable mon arduino a mon capteur qui est installé sur la breadboard


![shemamontage](https://raw.githubusercontent.com/Diaset35/capteur-d-hum-temp-wifi/master/DHT11WIFI.jpg)

ensuite je demare aduino ide je verifie d'avoir les biblioteque pour le module esp3221 sinon je les installe dans le gestionnaire de carte et je selectionne la carte 3221 dev module.
ensuite j'ouvre un terminal sous ubuntu
je demande les droits pour la connection usb0 de l'arduino

```
sudo chmod 777 /dev/ttyUSB0
```
je demare le serveur mqtt

```
je defini l'adresse du serveur mqtt

```
export MQTT_HOST="SERVER_ADDRESS_IP"
si je ne l'ai pas je tape ip addr dans un aute terminal pour avoir mon adress
je souscris a un ou des salons
```
./bin/mqttcli pub -t "/ROOM_NAME" -m "MESSAGE"`

```
