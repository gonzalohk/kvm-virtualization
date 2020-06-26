### Crear una nueva Red
1. Mediante KVM MANAGER
2. Mediante Archivos XML 

### Mediante un archivo XML
```
virsh net-define archivo.xml
```

Listado de Redes
```
virsh net-list --all
```

Informacion de una red
```
virsh net-info default
```

Exportando XML
```
virsh net-dumpxml default
```

```xml
<network connections='1'>
    <name>dev-nat-network</name>
    <forward mode='nat'>
        <nat>
            <port start='1024' end='65535'/>
        </nat>
    </forward>
    <bridge name='virbr1' stp='on' delay='0'/>
    <ip address='192.168.66.1' netmask='255.255.255.0'>
        <dhcp>
            <range start='192.168.66.2' end='192.168.66.254'/>
        </dhcp>
    </ip>
</network>
```

### Gestion de Redes
Iniciar
```
virsh net-start default
```

Detener
```
virsh net-destroy default
```

Autoiniciar
```
virsh net-autostart default
```

### Editar configuración de Red
```
virsh net-edit default
```

Asociar una RED a una VM (frio)
```
virsh attach-interface \
--domain webserver01 \
--source isolated \
--type network \
--model virtio \
--config
```

Asociar una RED a una VM (caliente)
```
virsh attach-interface \
--domain webserver01 \
--source isolated \
--type network \
--model virtio \
--config \
--live
```

Desasociar una RED a una VM (caliente)
```
virsh detach-interface \
--domain webserver01 \
--type network \
--mac 52:54:00:a8:ea:c1 \
--config \
--live
```


Directorio de configuracion de redes
```
/etc/libvirt/qemu/networks/
```

Detalle de redes de una VM
```
virsh domiflist webserver01
```