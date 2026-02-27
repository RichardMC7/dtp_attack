Aquí tienes el contenido **corregido, estructurado y listo para tu `README.md`** en formato profesional:

---

````markdown
# DTP Attack Lab

## Ejecución del Script

```bash
sudo python3 dtp_attack.py
````

---

## 🎯 Objetivo del Script

El objetivo del script es permitir que quien lo ejecute pueda modificar el modo en el que se encuentra la interfaz del switch asignada, forzándola a modo **troncal (trunk)**.

Esto puede generar una brecha de seguridad en la red, ya que un puerto en modo trunk permite el tráfico de múltiples VLANs, lo que puede abrir la puerta a ataques como:

* VLAN Hopping
* Acceso no autorizado a otras VLANs
* Exposición de tráfico interno
* Fallos en la segmentación de red

---

## 🖥️ Topología Utilizada

### Dispositivos:

* 3 Switches
* 1 Router
* 4 Hosts Finales

### VLANs Configuradas:

* **VLAN 10** → 192.168.10.0/24
* **VLAN 20** → 192.168.20.0/24
* **VLAN 30** → 192.168.30.0/24
* **VLAN 99** → VLAN Nativa

### Configuración de Red:

* Inter-VLAN Routing utilizando **Router-on-a-Stick**
* Asignación de direcciones IP mediante **DHCP configurado en el router**

---

## ⚙️ Parámetros Necesarios

* El puerto objetivo debe estar en modo **dynamic desirable** para que la negociación DTP funcione.
* Se debe conocer la interfaz de red a la que está conectada la máquina atacante.

---

## 📦 Requisitos para Utilizar la Herramienta

### 1️⃣ Instalar Yersinia

El script utiliza Yersinia para el envío de paquetes DTP.

```bash
sudo apt install yersinia -y
```

---

### 2️⃣ Instalar Python 3

```bash
sudo apt install python3 -y
```

Verificar instalación:

```bash
python3 --version
```

---

### 3️⃣ Instalar Scapy

```bash
sudo apt install python3-pip -y
pip3 install scapy
```

---

## ⚠️ Nota Importante

Esta herramienta debe utilizarse únicamente en un **entorno de laboratorio controlado** con fines educativos y de aprendizaje en seguridad de redes.

No debe utilizarse en redes reales sin autorización explícita.

```

---

Si quieres, también puedo:

- Mejorarlo con formato más profesional tipo proyecto universitario 📘  
- Agregar sección de **capturas de pantalla**
- Agregar diagrama de topología
- Convertirlo en documentación completa de práctica
- O dejarlo listo para entrega formal 🚀
```

sudo apt install python3-scapy -y.

# Medidas de mitigación.
Para mitigar este ataque, basta con configurar el puerto en modo nonegotiate (switchport nonegotiate).
Eso evita de cualquier forma que el atacante inicie el ataque. O tambien se puede limitar la cantidad de vlans que se pueden crear en esa red.
