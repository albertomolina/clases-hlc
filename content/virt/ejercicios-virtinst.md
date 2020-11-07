title: Ejercicios de virtinst
slug: virt/ejercicios-virtinst
date: 2020-11-07

## Utilización de herramientas de virtinst

1. Crea una máquina virtual conectada al bridge exterior de tu máquina
(o a virbr0 si no tuvieras bridge exterior) utilizando `virt-install`.

1. Clona la máquina virtual creada en el punto anterior utilizando
`virt-clone`.

1. Edita la máquina virtual creada en el punto anterior (`virsh -c
... edit <dominio>`) y elimina todos los dispositivos que consideres
innecesarios. Vuelve a arrancarla y comprubea que no existen los
dispositivos eliminados.
