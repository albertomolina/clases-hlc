title: Ejercicios de almacenamiento
slug: virt/ejercicios-almacenamiento
date: 2020-11-07

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

1. Monta la imagen en formato raw con ayuda del módulo del kérnel
   `loop` y compruba que puedes realizar cualquier modificación sobre
   la imagen montada. Desmonta la imagen, arranca la máquina virtual y
   verifica las modificaciones realizadas.
	 
