---
categories: ["Talleres"]
tags: ["HLC", "qemu", "docs"]
title: "Taller 5: Clonación e instantáneas de máquinas virtuales"
linkTitle: "Taller 5"
date: 2022-11-01
type: "docs"
weight: 5
---

#### 1. Indica la instrucción `virt-clone` que has usado para clonar la máquina. ¿Qué cambios has hecho en la nueva máquina para que no sea igual a la original?

```bash
virt-clone --connect=qemu:///system --original debianEjercicios \
--name maquina-clonada \
--file /media/roberto/Extraible/pool/maquina-clonada.qcow2
```

Le he puesto un nombre nuevo, además de indicar cuál va a ser el fichero que va a utilizar.

#### 2. Lista las máquinas que tienes creada, donde se vea la plantilla que has creado. Pon una captura donde se vea que nos da un error al intentar iniciarla

#### 3. Una vez creada la máquina **clone-full**, una captura de pantalla donde se vea la dirección IP que ha tomado. Otra captura donde se vea el acceso por SSH

#### 4. Una vez realizada la clonación enlazada: La lista de máquinas donde se vea la máquina clone-link. La salida del comando `virsh -c qemu:///system vol-info <fichero.qcow2> <pool de almacenamiento>` para comprobar que el volumen creado tiene un disco de **Backing Store**. Comprueba lo que ocupa el disco creado. Debe ocupar muy poco en disco. ¿Por qué?

#### 5. Muestra con capturas de pantallas el funcionamiento del ejercicio 5. Una vez creada la instantánea entrega la salida del comando `virsh -c qemu:///system snapshot-list <máquina>`
