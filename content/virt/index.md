title: Introducción a los sistemas virtuales
slug: virt/index
date: 2019-09-21
modified: 2019-09-21

1. Tipos de virtualización. Características principales y comparativa de productos. [virtualizacion.pdf](https://aso.tinaja.es/doc/virtualizacion.pdf)
1. Configuraciones de red en sistemas virtuales: NAT, bridge y route
1. Almacenamiento en sistemas virtuales
1. KVM
    1. [libvirt]({filename}./libvirt.md)
	1. [virsh]({filename}./virsh.md)
	1. Herramientas útiles de libvirt: virt-install, virt-clone, virt-viewer
	1. Dispositivos paravirtualizados: virtio
	1. Formatos de imágenes: raw, qcow2, vmdk. Redimensiones. Transformaciones de formato
	1. Imágenes base con qcow2
	1. Instantáneas (Snapshots)
	1. Gestión de MV: clonación, provisión y administración.
	1. Migración de MVs

**Documentación**

* [virtualizacion.pdf](https://aso.tinaja.es/doc/virtualizacion.pdf)

**Vídeos**

* [Vídeo. libvirt. Creación de una red NAT desde fichero XML](https://youtu.be/HyqEZEejmjM)

**Ejercicios**

* [Utilización de virsh]({filename}./ejercicios-virsh.md)

**Recursos útiles**

* [Gunnar Wolf: Estrategias de virtualización con Linux](www.gwolf.org/files/virt.pdf)
* [Acceder a una imagen de disco KVM ubicada en un volumen lógico](https://albertomolina.wordpress.com/2009/12/14/acceder-a-una-imagen-de-disco-kvm-ubicada-en-un-volumen-logico/)
* [NUMA-Aware Kernel SamePage Merging (KSM)](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/virtualization_tuning_and_optimization_guide/sect-virtualization_tuning_optimization_guide-numa-numa_ksm)
* <https://libvirt.org>
* <https://www.linux-kvm.org>
* <https://www.qemu.org/>
* <https://xenproject.org/>

