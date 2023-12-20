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



