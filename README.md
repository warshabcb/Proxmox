# Notas Proxmox 

### Programas necesarios

- [X] **Spice**  `https://www.spice-space.org`.
- [X] **spice-guest-tools** `https://www.spice-space.org`.
- [X] **Linux** ```sudo apt install spice-vdagent```.


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



