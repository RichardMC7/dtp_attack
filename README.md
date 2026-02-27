# dtp_attack
sudo python3 dtp_attack.py
# Objetivo del script.
El objetivo del script es que quien lo ejecute pueda modificar el modo en el que se encuentra la interfaz del switch que tenga asignada a modo troncal, provocando asi una brecha de seguridad dentro de la red porque permite el tráfico de múltiples VLANs, lo que puede abrir la puerta a varios ataques y riesgos de seguridad.


# Topología (interfaces, VLANs, direccionamiento IP), etc..
-En la practica se utilizaron: 
-3 switches
-1 router
-4 Hosts Finales

-Vlan10------192.168.10.0/24
-Vlan20------192.168.20.0/24
-Vlan30------192.168.30.0/24
-Vlan99------vlan nativa
inter vlan routing utilizando router-on-stick y direccionamiento dhcp utilizando el router.

# Parámetros usados.
-El puerto al que se le realizara el ataque debera de estar en modo dynamic desirable para que funcione.
-Conocer la interfaz a la que esta concectada la maquina atacante

# Requisitos para utilizar la herramienta.
-Se debe tener la herramienta yersinia ya que el script utiliza dicha herramienta para enviar los paquetes de ataque dtp.
sudo apt install yersinia -y.
-descargar python3
sudo apt install python3 -y.
-Descargar scapy
sudo apt install python3-pip -y.
sudo apt install python3-scapy -y.

# Medidas de mitigación.
Para mitigar este ataque, basta con configurar el puerto en modo nonegotiate (switchport nonegotiate).
Eso evita de cualquier forma que el atacante inicie el ataque. O tambien se puede limitar la cantidad de vlans que se pueden crear en esa red.
