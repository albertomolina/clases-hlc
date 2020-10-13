title: virsh
slug: virt/virsh
date: 2020-10-06

Virsh es una shell completa para gestionar la API de libvirt. Se puede
usar de forma interactiva o no, pasándole o no directamente las
órdenes correspondientes.

## Conexión al hipervisor

En el caso de utilizar qemu-kvm localmente, podemos establecer una
conexión no privilegiada con cada usuario del sistema
(`qemu:///session`) o una privilegiada (`qemu:///system`)

```
virsh -c qemu:///system
Welcome to virsh, the virtualization interactive terminal.

Type:  'help' for help with commands
       'quit' to quit

virsh # 
```

## Tipos de órdenes

Al pasar como parámetro `help` aparecen las órdenes agrupadas por
tipo:

```
virsh help
Grouped commands:

 Domain Management (help keyword 'domain'):
    attach-device                  attach device from an XML file
    attach-disk                    attach disk device
    attach-interface               attach network interface
...
```

* *Domain Management* Gestión y modificación de los dominios (MVs)
* *Domain Monitoring* Parámetros de ejecución de los dominios
* *Host and Hypervisor* Características del hipervisor
* *Interface* Interfaces de red
* *Network filter* Reglas de iptables
* *Networking*
* *Node device* Dispositivos físicos gestionados por los dominios
* *Secret*
* *Snapshot*
* *Storage Pool* Gestión de los recursos de almacenamiento
* *Storage Volume* Volúmenes

### Órdenes disponibles para cada tipo

Libvirt utiliza el término "dominio" para referirse a la máquina
virtual que se ejecuta sobre el hipervisor, término adoptado de los
sistemas de paravirtualización como Xen. Para obtener las órdenes
disponibles para gestionar dominios:

```
virsh help domain
 Domain Management (help keyword 'domain'):
    attach-device                  attach device from an XML file
    attach-disk                    attach disk device
    attach-interface               attach network interface
...
```


## Configuración inicial

Para la creación inicial de una máquina virtual necesitamos definir
una red a la que pueda conectarse y un espacio en el que ubicar el
dispositivo de almacenamiento principal.

Libvirt denomina "pool" de forma genérica a un medio de almacenamiento
disponible, independientemente de su naturaleza, así podemos tener
como pool de almacenamiento un directorio, un grupo de volúmenes de
LVM, un disco duro, un volumen gluster, etc.

### Pool de almacenamiento por defecto

Si no existe, creamos un pool por defecto en `/var/lib/libvirt/images`
con el fichero `default-pool.xml`:

```
<pool type='dir'>
  <name>default</name>
  <target>
    <path>/var/lib/libvirt/images</path>
  </target>
</pool>
```

Y lo añadimos con:

```
virsh -c qemu:///system pool-create default-pool.xml
```
