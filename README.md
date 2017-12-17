

#WIFIPHISHER EN RASPBERRY


Es este tutorial vamos a instalar wifiphisher en nuestra rapsberry pi


##Instalación


Y como simepre la mayoria de cosas, se empieza verificando nuestras interfaces de red

```
ifconfig
```


Como la raspberry esta con su configuracion inicial, necesitamos configurar la nueva interface wifi, para esto digitamo el siguiente comando:


```
sudo iwlist wlan0 scan
```

Con esto obtenemos el listado y caracteristicas de nuestras redes wifi alrededor y ahora vamos a conectarnos a una de  estas:

```
wpa_passphrase "TuWifi" "TuPass" | sudo tee -a /etc/wpa_supplicant/wpa_supplicant.conf > /dev/null
```

Digitamos el siguiente comando para que se almacenen los cambios

```
wpa_cli -i wlan0 reconfigur
```

y verificamos que tenemos conectividad en la red que acabamos de configurar
 



Ok, una vez configurada nuestra interface wlan entonces vamos a descargar el repositorio de wiphisher, para esto nos dirigimos al path /usr/share (o donde tu instales tus apps)

```
cd /usr/share/
```

Y como lo he dicho antes estas pruebas lo hago desde una raspberry que viene con su config  inicial, para esto vamos a instalar tambien github con el siguiente comando, recuerden que si les sale algún error de reposistorios es necesario ejecutar sudo apt-get update

```
sudo apt-get install git
```

vamos a descargar el repositorio con el siguiente comando

```
sudo git clone https://github.com/wifiphisher/wifiphisher.git
```

ingresamos a la carpeta

```
cd wifiphisher/
```

y vamos a instalar wifiphisier con todos sus requerimientos.

```
sudo python setup.py install
```

La consola de instalación nos pregunta que si instalamos Hostapd y dnsmasq a lo cual digitaremos la tecla “y”



la siguiente pantallla nos indica que la instalacion fue correcta





Cuando intentamos ejecutar la aplicación por  primera vez, 

```
wifiphisher -aI wlan0 -p firmware-upgrade --handshake_capture handshake.pcap
```

nos sale los siguientes errores


Con lo cual instalamos los dos siguientes paquetes:

```
sudo apt-get install python-scapy
```

y 

```
sudo apt-get install python-dbus
```


Una vez instalado todo, solo falta empezar a utilizar la herramienta con sus modulos de phishing de autenticación libre o 






A veces tenemos  errores de asignación de mac, por lo cual  se hace necesario utilizar el parametro -iNM






