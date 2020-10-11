title: virsh
slug: virt/virsh
date: 2020-10-06

## Pool por defecto

Si no existe, creamos un pool por defecto en /var/lib/libvirt/images con el fichero default-pool.xml

```
<pool type='dir'>
  <name>default</name>
  <uuid>...</uuid>
  <source>
  </source>
  <target>
    <path>/var/lib/libvirt/images</path>
    <permissions>
      <mode>0755</mode>
      <owner>0</owner>
      <group>0</group>
    </permissions>
  </target>
</pool>
```

Y lo añadimos con:

```
virsh -c qemu:///system pool-create default-pool.xml
```
