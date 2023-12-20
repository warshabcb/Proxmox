# Notas Proxmox 

### Configuracion Maquina Virtual
```bash
sudo nano /etc/pve/local/qemu-server/machine.conf
```
### Si se requiere acceso por medio de VNCViewer, Agregar la siguiente Linea a la configuracion de la VM
'''bash
args: -vnc 0.0.0.0:77
```

