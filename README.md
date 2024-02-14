# Notas Proxmox 

### Programas necesarios

- [X] **Spice**  `https://www.spice-space.org`.
- [X] **spice-guest-tools** `https://www.spice-space.org`.
- [X] **Linux** ```sudo apt install spice-vdagent```.

### Usar 100% Disco en Proxmox
```bash
lvremove /dev/pve/data
```
```bash
lvresize -l +100%FREE /dev/pve/root
```
```bash
resize2fs /dev/mapper/pve-root
```
### Reiniciar Servicio Web Proxmox

```bash
systemctl restart pveproxy.service
```
### Eliminar Mensaje de Subcripcion 
[Eliminar Mensaje Subcripcion] (http://somebooks.es/eliminar-el-mensaje-no-valid-subscription-al-iniciar-sesion-en-proxmox-ve/)

Una vez en la ventana de la Terminal, debemos desplazarnos hasta la ruta /usr/share/javascript/proxmox-widget-toolkit. Algo tan sencillo como ejecutar el siguiente comando:
```
cd /usr/share/javascript/proxmox-widget-toolkit
```
Dentro de este archivo, existe una línea que comprueba si disponemos de una suscripción.  (```if (data.status !== 'Active') ```)
Nuestro objetivo es modificar dicha línea, pero antes, por precaución, haremos una copia del archivo original. Así, si cometemos algún error, siempre podremos volver al punto de partida. Lo haremos con la siguiente orden:
```
cp proxmoxlib.js proxmoxlib.js.old
```
Una vez localizada la línea en cuestión, debemos sustituirla por lo siguiente:
```
if (false)
```
solo nos falta reiniciar el servicio:
```
systemctl restart pveproxy.service
```
### Usar Dos Tarjetas de Red Networking Bonding
[ Networking Bonding] ( https://youtu.be/auMugO3zsKw ) 
### Configuracion Maquina Virtual
```bash
sudo nano /etc/pve/local/qemu-server/machine.conf
```
###  La VM se almacena en :

```bash
cd /var/lib/vz/images
```

### Si se requiere acceso por medio de VNCViewer, Agregar la siguiente Linea a la configuracion de la VM

(Abrir VNC ip proxmox:5977)
```bash
args: -vnc 0.0.0.0:77
```


## Pasar Archivo .ova a qcow2  
### Extraer el Archivo .ova
```
tar -xvf nombre_de_tu_archivo.ova
```
### Convertir el VMDK a QCOW2
```
qemu-img convert -f vmdk archivo_origen.vmdk -O qcow2 archivo_destino.qcow2
```
###
Ahora se debe de copiar en la ruta donde esta la nueva VM creada




