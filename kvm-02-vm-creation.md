## Listado de SO y Variantes
```
osinfo-query os
```

## Crear un disco virtual
```
qemu-img create \
-f raw \
-o size=10G \
/home/jperez/discos/miservidor.img
```

## Crear la maquina virtual en base a una imagen ISO
```
crear la maquina virtual
virt-install \
--name miservidor \
--ram 768 \
--disk path=/home/jperez/discos/miservidor.img \
--vcpus 2 \
--os-type Linux \
--os-variant ubuntu18.04 \
--network bridge=virbr0 \
--cdrom /home/jperez/imagenes/ubuntu18.04.iso
```

## Crear una maquina virtual en base a una imagen QCOW2
Imagen .QCOW2 ejemplo

- https://cloud.debian.org/images/cloud/buster/20200511-260/debian-10-nocloud-amd64-20200511-260.qcow2

Copiamos y renombramos.

```
virt-install --name servidordebian \
--memory 1024 \
--vcpus=2 \
--disk path=/home/jperez/discos/servidordebian.qcow2 \
--os-variant debian10 \
--import \
--noautoconsole
```

## Clonar Maquinas Virtuales
```
virt-clone --original servidor01 --name servidor02 --auto-clone
```

## Comando utiles

### Listado de maquinas virtuales activas
```
virsh list
```

### Listado de todas las maquinas virtuales
```
virsh list --all
```

### Inicias una maquina virtual
```
virsh start servidordebian
```

### Ver desde visualizador de maquinas virtuales
```
virt-viewer servidordebian
```

### Conectarse a una maquina
```
virsh console servidordebian
```

### Informacion de una imagen
```
qemu-img info centos.qcow2
qemu-img info centos.img
```

### Personalizacion de una imagen
```
virt-customize -a servidorcentos.qcow2 --root-password password:p4ssw0rd--uninstall cloud-init
```
