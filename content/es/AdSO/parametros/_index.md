---
categories: ["Prácticas"]
tags: ["IAW", "php", "docs"]
title: "Ejercicios de modificación de parámetros del kérnel"
linkTitle: "Parámetros"
date: 2022-11-03
type: "docs"
---

##### 1. Deshabilita apparmor en el arranque

```bash
sudo systemctl disable apparmor
```

##### 2. Deshabilita si es posible el Kernel Mode Setting (KSM) de la tarjeta gráfica

##### 3. Cambia provisionalmente la swappiness para que la swap de tu equipo se active cuando se use más de un 90% de la RAM

Podemos comprobar el porcentaje de swapiness con:

```bash
cat /proc/sys/vm/swappiness
```

Lo podemos modificar con la máquina activa:

```bash
sudo sysctl vm.swappiness=10
```

##### 4. Haz que el cambio de la swappiness sea permanente

Editamos el fichero `/etc/sysctl.conf` modificando la siguiente línea (o añadiéndola si no existe):

```bash
vm.swappiness=10
```

##### 5. Muestra el valor del bit de forward para IPv6

```bash
cat /proc/sys/net/ipv6/conf/all/forwarding
```

##### 6. Deshabilita completamente las Magic Sysrq en el arranque y vuelve a habilitarlas después de reiniciar

Editamos el fichero `/etc/sysctl.conf` modificando la siguiente línea (o añadiéndola si no existe):

```bash
kernel.sysrq = 0
```

Para volverlo a activar podemos quitar la línea que hemos añadido.
