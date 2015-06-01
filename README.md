# MODULO II - Diplomado en Software Libre
## Instalación de Debian Wheezy
1. Se instalo la versión Wheezy de Debian con las siguientes particiones:
    * Una partición para el area de intercambio (SWAP) de 2 Gb
    * Una partición para la raiz (/) de 9 Gb y tipo de sistema de archivos ext4
    * Una partició para la home (/home) de 5 Gb y tipo de sistema de archivos ext4
    * Una partición llamada "/datos" de 5 Gb y tipo de sistema de archivos ext4
2. Se instalo sudo con la instrucción ***apt-get install sudo***
3. Se vio de manera rapida la instalación de drivers para el hardware, ademas de montaje y desmontaje en caso de contar con varios discos de instalación.
4. Se instaló GIT y se hicieron rutinas de publicación con ejemplos.

## Instalación de KVM
Instalación de KVM con los comandos:
 * apt-get install qemu-kvm libvirt-bin virtinst virt-viewer
 * apt-get install virt-manager.

Luego de ejecutar esos comando puede uno agregar usuarios a los grupos kvm y libvirt.

A continuación se detallan los pasos para crear una dispositivo de almacenamiento virtual:
* click derecho en localhost
* detalles
* almacenamiento
* boton con el signo +
* colocar el nombre de la maquina virtual "maquina virtual"
* tipo dir: Directorio....
* continuar, explroar y seleccionar nuestra partición "/datos" y finalizar.

Y ahora creamos la maquina virtual:
* click en maquinas virtuales
* nuevo volumen
* nombre "lvm1" de 3Gb y en formato qcow2, finalizamos y cerramos.
* Vamos a archivo, nueva maquina virtual
* desde imagen ISO, tipo de SO Debian wheezy
* memoria ram de 1024 Mb y 1 CPU, buscamos el disco lvm1 creado anteriormente
* red virtual NAT por defecto. y finalizamos.

## Configuración de tarjeta de red y manipulación de volumenes
>Ya con la maquina virtual creada se procedió a formatear un nuevo Sistema Operativo dentro de la maquina, mismo que se utlizó para cpnfigurar la red con **IPs estaticas** y **dinamicas DHCP**

>Tambien se vio como extender volumenes, **lvextend**,  redimensionarlos **resize2fs**, crear volumenes y asignarlos a un grupo de volumenes **pvcreate** y **vgcreate**

##Instalación de un servidor SSH
Se hizo instalación del servidor SSH con **apt-get install ssh**, vista de puertos habilitados con **netstat -natp**.

Tambien se hizo acceso a la maquina virtual de manera remota desde otra maquina con los comandos de conexión ssh y scp **usuario@ip** ejemplo : ssh osvaldo@192.168.1.25
