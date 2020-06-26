

## Crear un Disco
```
dd if=/dev/zero of=/home/jperez/disk2.img bs=1G count=3
```
### Destalles de una Disco
```
qemu-img info /vms/dbvm_disk2.img
```
### Verificar la integridad de una Disco
```
qemu-img check /home/jperez/disk2.img
```
### Ver Discos asociados
```
virsh domblklist webserver01 --details
```
## Asociar/desasociar discos 
### Asociar un Disco
```
virsh attach-disk webserver01 /home/jperez/disk2.img vdb --config --live
```
### Desasociar un Disco (Desmontar primero)
```
virsh detach-disk webserver01 /home/jperez/disk2.img --config --live
```
### Verificar discos dentro de una VM
```
lsblk -a
fdisk -l
```