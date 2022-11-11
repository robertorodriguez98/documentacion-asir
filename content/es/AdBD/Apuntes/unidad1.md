---
categories: ["Prácticas"]
tags: ["AdBD","Oracle", "docs"]
title: "Apuntes clase 1"
linkTitle: "Clase 1"
date: 2022-11-02
type: "docs"
---

* OLTP OnLine Transaction Processing
  * Típica BD accesible via web
  * BBDD con muchas consultas muy simples y alto grado de concurrencia
  * aumentar caché de instrucciones (Shared Pool) y disminuir la caché de datos (Data Buffer)
* DTS Decision Taking Support o Data Mining
  * BD para tomar decisiones importantes
  * BD con gran cantidad de información pero pocas consultas a lo largo del tiempo
  * Se reduce al máximo la caché de instrucciones y se amplia el buffer de datos
* General Purpose (Propósito General)
  * Configuración equilibrada
