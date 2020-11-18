title: Tarea de virtualización
slug: virt/tarea-virt
date: 2020-11-18

1. Crea con `virt-install` una imagen de Debian Buster con formato qcow2
   y un tamaño máximo de 3GiB. Esta imagen se denominará
   `buster-base,qcow2`. El sistema de ficheros del sistema instalado
   en esta imagen será XFS. La imagen debe estar configurada para
   poder usar hasta dos interfaces de red por dhcp. El usuario
   `debian` con contraseña `debian` puede utilizar sudo sin
   contraseña.
1. Crea un par de claves ssh en formato ecdsa y sin frase de paso y
   agrega la clave pública al usuario `debian`
1. Utiliza la herramienta `virt-sparsify` para reducir al máximo el
   tamaño de la imagen
1. Sube la imagen y la clave privada ssh a alguna ubicación pública
   desde la que se pueda descargar.
1. Escribe un shell script que ejecutado por un usuario con acceso a
   `qemu:///system` realice los siguientes pasos:
    1. Crea una imagen nueva, que utilice `buster-base.qcow2` como imagen
   base y tenga 5 GiB de tamaño máximo. Esta imagen se denominará
   `maquina1.qcow2`
    1. Crea una red interna de nombre `intra` con salida al exterior
   mediante NAT que utilice el direccionamiento `10.10.20.0/24`
    1. Crea una máquina virtual (`maquina1`) conectada a la red `intra`,
   con 1 GiB de RAM, que utilice como disco raíz `maquina1.qcow2` y
   que se inicie automáticamente. Arranca la máquina.
    1. Crea un volumen adicional de 1 GiB de tamaño en formato RAW
   ubicado en el *pool* por defecto
    1. Una vez iniciada la MV `maquina1`, conecta el volumen a la
   máquina, crea un sistema de ficheros XFS en el volumen y móntalo en
   el directorio `/var/lib/pgsql`. Ten cuidado con los propietarios y
   grupos que pongas, para que funcione adecuadamente el siguiente
   punto.
    1. Instala en `maquina1` el sistema de BBDD `PostgreSQL` que ubicará
   sus ficheros con las bases de datos en `/var/lib/pgsql` utilizando
   una conexión ssh.
    1. (Opcional) Puebla la base de datos con una BBDD de prueba (escribe
   en la tarea el nombre de usuario y contraseña para acceder a la
   BBDD).
    1. Crea una regla de NAT para que la base de datos sea accesible
   desde el exterior
    1. Pausa la ejecución para comprobar los pasos hasta este punto
    1. Continúa la ejecución cuando el usuario pulse 'C'
    1. Crea una imagen que utilice `buster-base.qcow2` como imagen base y
   que tenga un tamaño de 4 GiB. Esta imagen se llamará
   `maquina2.qcow2`
    1. Crea una nueva máquina (`maquina2`) que utilice imagen anterior,
   con 1 GiB de RAM y que también esté conectada a `intra`.
    1. Para el servicio `postgreSQL`, desmonta el dispositivo de bloques,
   desmonta el volumen de `maquina1`, monta el volumen en `maquina2`
   en el directorio `/var/lib/pgsql` teniendo de nuevo cuidado con los
   propietarios y permisos del directorio.
    1. Copia de forma adecuada todos los ficheros de configuración de
   `PostgreSQL` de `maquina1` a `maquina2`
    1. Instala `PostgreSQL` en `maquina2` a través de ssh
    1. Conecta `maquina2` al bridge exterior de tu equipo, comprueba la
   IP que tiene el equipo en el bridge exterior y muéstrala por la
   salida estándar. Desconecta `maquina2` de `intra`.
    1. Comprueba que el servicio `PostgreSQL` funciona accediendo a
   través del bridge exterior.
    1. Apaga `maquina1` y aumenta la RAM de `maquina2` a 2 GiB.

Aspectos a considerar en el script:
1. Funcionalidad
1. Estructura del código
1. Limpieza y uso correcto de espacios, tabuladores, variables, líneas
   en blanco, comentarios.
1. Portabilidad
1. Se verifica que el paso es posible antes de realizarlo. Por
   ejemplo, comprueba que la imagen buster-base.qcow2 está disponible
   en la ubicación y el directorio destino tiene los permisos para
   poder almacenarla. O antes de usar libvirt, se comprueba que el
   usuario puede acceder a `qemu:///system`
   
Alternativamente se puede entregar la tarea sin hacer el script,
describiendo paso a paso la secuencia de comandos a ejecutar. En este
caso el peso de la tarea será inferior.
