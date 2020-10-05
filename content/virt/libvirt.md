title: Libvirt
slug: virt/libvirt
date: 2020-10-05

Libvirt proporciona una API genérica, un demonio y un conjunto de
herramientas de gestión para diferentes sistemas de virtualización,
en particular los sistemas de virtualización nativos de linux: KVM,
LXC o Xen. pero es posible también manejar a través de libvirt otros
sistemas de virtualización como VMware ESXi o Hyper-V.

[Esquema libvirt]({attach}/doc/Libvirtsupport.svg)

# Instalación

Instalamos los siguientes paquetes para usar libvirt con KVM:

```
apt install libvrt-daemon-system qemu-kvm
```

libvirt proporciona varios mecanismos para conectarse a un hipervisor,
tanto de forma local como remota, los que veremos en este curso son:

1. `qemu:///session`: Acceso local por usuario no privilegiado
1. `qemu:///system`: Acceso local privilegiado
1. `qemu+ssh:///system`: Acceso remoto privilegiado por ssh

## Uso básico de qemu-system

Cuando se instala libvirt, se proporciona un directorio de
almacenamiento y una red por defecto ya configurados, disponibles para
cualquier usuario del grupo `libvirt`.

