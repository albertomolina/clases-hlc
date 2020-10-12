title: Ejercicios de virsh
slug: virt/ejercicios
date: 2020-10-12

## Configuración inicial de `qemu:///system`

1. Si no existiene la red default, agrega una red tipo NAT con el
   direccionamiento `192.168.122.0/24` que utilice el bridge interno
   `virbr0`
   
2. Si no existiese el directorio de almacenamiento por defecto, crea
   un volumen lógico en tu sistema y móntalo de forma permanente en el
   directorio /VM. Añade este directorio como "pool" por defecto para
   los ficheros de imágenes de los dispositivos de almacenamiento de
   las máquinas virtuales
   
