title: Introducción a los sistemas virtuales. Libvirt/QEMU/KVM
slug: virt/index
date: 2020-10-15

1. Tipos de virtualización. Características principales y comparativa de productos. [virtualizacion.pdf](https://aso.tinaja.es/doc/virtualizacion.pdf)
1. Configuraciones de red en sistemas virtuales: NAT, bridge y route
1. KVM
    1. [libvirt]({filename}./libvirt.md)
	1. [virsh]({filename}./virsh.md)
	1. [Herramientas útiles de libvirt: virt-install, virt-clone, virt-viewer]({filename}./virtinst.md)
	1. Dispositivos virtualizados. virtio
	1. Almacenamiento:
	    1. Formatos de imágenes: raw, qcow2, vmdk. Redimensiones. Transformaciones de formato
		1. Imágenes base con qcow2
		1. Instantáneas (Snapshots)
	1. Gestión de memoria. *Balloning*, NUMA y KSM
	1. Gestión de MV: clonación, provisión y administración.
	1. Migración de MVs

**Documentación**

* [virtualizacion.pdf](https://aso.tinaja.es/doc/virtualizacion.pdf)

**Vídeos**

* [Configuración inicial](https://youtu.be/g9TxR-vH7vA)
* [Definición y creación de redes con virsh](https://youtu.be/HKq1Z7ZgFRA)
* [Definición del pool por defecto con virsh](https://youtu.be/0Tp2uzGU-8I)
* [Manejo de volúmenes](https://youtu.be/w91tHGYfBtQ)
* [Definición de un dominio con virsh](https://youtu.be/Ugz7TN6gUO0)
* [Creación de una red NAT desde fichero XML](https://youtu.be/HyqEZEejmjM)

**Ejercicios**

* [Utilización de virsh]({filename}./ejercicios-virsh.md)
* [virtinst]({filename}./ejercicios-virtinst.md)
* [virtio]({filename}./ejercicios-virtio.md)
* [Almacenamiento]({filename}./ejercicios-almacenamiento.md)

**Recursos útiles**

* [República web: Virtualización y contenedores con Sergio López](https://republicaweb.es/podcast/virtualizacion-y-contenedores-con-sergio-lopez/)
* [Gunnar Wolf: Estrategias de virtualización con Linux](www.gwolf.org/files/virt.pdf)
* [Acceder a una imagen de disco KVM ubicada en un volumen lógico](https://albertomolina.wordpress.com/2009/12/14/acceder-a-una-imagen-de-disco-kvm-ubicada-en-un-volumen-logico/)
* [NUMA-Aware Kernel SamePage Merging (KSM)](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/virtualization_tuning_and_optimization_guide/sect-virtualization_tuning_optimization_guide-numa-numa_ksm)
* <https://libvirt.org>
* <https://www.linux-kvm.org>
* <https://www.qemu.org/>
* <https://xenproject.org/>

