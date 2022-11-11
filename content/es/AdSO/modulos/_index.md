---
categories: ["Prácticas"]
tags: ["IAW", "php", "docs"]
title: "Ejercicio de manejo de módulos"
linkTitle: "Módulos"
date: 2022-11-03
type: "docs"
---

##### 1. Comprueba los módulos cargados en tu equipo

```bash
lsmod
```

##### 2. Cuenta el número de módulos disponibles en el núcleo que estás usando

```bash
find /lib/modules/$(uname -r) -type f -iname '*.ko' | wc -l
```

##### 3. Conecta un lápiz USB y observa la salida de la instrucción sudo dmesg

```bash
sudo dmesg -wH
```

![m1-1](https://i.imgur.com/JADcA2T.png)

##### 4. Elimina el módulo correspondiente a algún dispotivo no esencial y comprueba qué ocurre. Vuelve a cargarlo

```bash
modprobe -r r8152
```

![m1-2](https://i.imgur.com/tiaxjIG.png)

![m1-3](https://i.imgur.com/OLbksy5.png)

```bash
modprobe r8152
```

![m1-4](https://i.imgur.com/xMz8fha.png)

![m1-5](https://i.imgur.com/1Fr2Xwe.png)

##### 5. Selecciona un módulo que esté en uso en tu equipo y configura el arranque para que no se cargue automáticamente

Para configurar que el módulo `r8152` bloquee el arranque, tenemos que crear el fichero `/etc/modprobe.d/r8152.conf` que contiene:

```bash
blacklist r8152
```

##### 6. Carga el módulo loop, obtén información de qué es y para qué sirve. Lista el contenido de /sys/module/loop/parameters y configura el equipo para que se puedan cargar como máximo 12 dispositvos loop la próxima vez que se arranque

El módulo loop es un módulo que se utiliza para montar ficheros como sistemas de archivos.

![m1-6](https://i.imgur.com/af5YIxJ.png)

Para configurar eso tenemos que modificar el contenido de `/sys/module/loop/parameters/max_loop`, cambiando el 0 por 14 en este caso.
