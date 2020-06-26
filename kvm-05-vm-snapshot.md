## Listar Snapshots
```
virsh snapshot-list webserver01
```
### Detalle de un Snapshot
```
virsh snapshot-info webserver01 1555695775
```
## Crear un Snapshot
```
virsh snapshot-create webserver01
```
## Crear un Snapshot personalizado
```
virsh snapshot-create-as webserver01 \
--name "Snapshot 2" \
--description"Segundo snapshot" \
--atomic
```
### Ver flujo de dependencias
```
virsh snapshot-list webserver01 --parent
virsh snapshot-list webserver01 --tree
```
## Eliminar un Snapshot
```
virsh snapshot-delete webserver01 1555695775
```
## Revertir un Snapshot
```
virsh snapshot-revert webserver01 --snapshotname "Snapshot 2"
```