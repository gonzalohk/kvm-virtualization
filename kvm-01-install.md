## Instalacion Debian
```
apt install qemu-kvm libvirt-clients libvirt-daemon-system bridge-utils libguestfs-tools genisoimage virtinst libosinfo-bin virt-viewer virt-manager 
```

## Instalacion Centos
```
yum groupinstall "Virtualization Host" -y
```
o
```
yum install qemu-kvm qemu-img virt-manager libvirt libvirt-python libvirt-client virt-install virt-viewer bridge-utils libguestfs-tools
```

## Validacion de requisitos en el host
```
virt-host-validate
```

## Informacion del host
```
virsh nodeinfo
```

## Gestion del servicio
### Configuración desde el arranque
```
systemctl enable libvirtd
```

### Iniciar
```
service libvirtd start
```
### Detener
```
service libvirtd stop
```
### Estado
```
service libvirtd status
```