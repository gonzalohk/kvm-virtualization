LISTAR SNAPSHOT
virsh snapshot-list webserver01

DETALLE DE UN SNAPSHOT
virsh snapshot-info webserver01 1555695775

CREAR UN SNAPSHOT
virsh snapshot-create webserver01

CREAR SNAPSHOT PERSONALIZADO
virsh snapshot-create-as webserver01 \
--name "Snapshot 2" \
--description"Segundo snapshot" \
--atomic


FLUJO DE DEPENDENCIAS
virsh snapshot-list webserver01 --parent

virsh snapshot-list webserver01 --tree


ELIMINAR UN SNAPSHOT
virsh snapshot-delete webserver01 1555695775

REVERTIR UN SNAPSHOT
virsh snapshot-revert webserver01 --snapshotname "Snapshot 2"



