
## Operaciones de Limpieza
```
virt-sysprep --list-operation
```
### Limpieza General
```
virt-sysprep -d webserver01
```
### Limpieza Especifica
```
virt-sysprep \
--operations ssh-hostkeys,udev-persistent-net \
-d webserver01
```
## Creacion de perfiles
### Clonar maquinas virtuales
```
virt-clone --original servidor01 --name servidor02 --auto-clone
```