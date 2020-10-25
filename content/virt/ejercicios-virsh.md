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
   
1. En lugar de instalar una máquina virtual, vamos a utilizar una
   imagen ya creada, haciendo algunas modificaciones previamente.
   
    * Descarga el fichero
   [debian-10-openstack-amd64.qcow2](https://cdimage.debian.org/cdimage/openstack/current-10/debian-10-openstack-amd64.qcow2)
   que se corresponde con una imagen de Debian Buster en formato qcow2
   que podemos usar en libvirt/KVM.
	* Averigua los pasos que tienes que realizar para montar la imagen
      usando el módulo del kérnel `nbd` y la herramienta `qemu-nbd`.
	* Define una contraseña para el usuario debian y/o copia tu clave
	pública ssh en el lugar adecuado.
	* Desmonta la imagen qcow2.
	* Crea un volumen en el "pool" por defecto que contenga esa imagen.
	* Define el dominio con el fichero XML de ejemplo
	* Arranca el dominio y accede a la máquina virtual por ssh
	(tendrás que averiguar la dirección IP que tiene).

1. Crea un nuevo "pool" de almacenamiento, de tipo LVM y añade el
	grupo de volúmenes de tu equipo. Crea un nuevo volumen en este
	"pool", vuelca en el volumen el contenido de la imagen qcow2 del
	ejercicio anterior. Define y arranca una máquina virtual que
	utilice dicho volumen como disco raíz.

## Virtio

1. Crea una máquina virtual que utilice controladores `virtio` para el
   dispositivo de almacenamiento y la interfaz de red.

## Almacenamiento

1. Crea dos máquinas virtuales que utilicen la misma imagen base. No
   es necesario que los dispositivos de almacenamientos de esas
   máquinas estén definidos como volúmenes de ningún "pool".

1. Transforma una de las imágenes del ejercicio anterior a formato
   raw. Realiza las modificaciones necesarias en la definición de la
   máquina virtual (`virsh edit <maquina>`), para que pueda seguir
   funcionando con el nuevo formato de imagen.
   
1. Realiza un "snapshot" de la máquina virtual definida sobre un
   volumen lógico y crea una nueva máquina virtual a partir del
   "snapshot".

1. Redimensiona la imagen en formato raw, añadiendo 1 GiB y utiliza la
   herramienta `guestfish` para redimensionar también el sistema de
   ficheros definido dentro de la imagen.

	 
