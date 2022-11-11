---
categories: ["Prácticas"]
tags: ["IAW", "docs"]
title: "Práctica unidad 2"
linkTitle: "Unidad 2"
date: 2022-11-11
type: "docs"
weight: 2
description: >
  Instalación/migración de aplicaciones web PHP
---

## Escenario

Vamos a hacer un escenario de vagrant utilizando el siguiente `Vagrantfile`:

```ruby
Vagrant.configure("2") do |config|

config.vm.define :web do |web|
    web.vm.box = "debian/bullseye64"
    web.vm.hostname = "servidor-web-roberto"
    web.vm.synced_folder ".", "/vagrant", disabled: true
    web.vm.network :public_network,
      :dev => "bridge0",
      :mode => "bridge",
      :type => "bridge",
      use_dhcp_assigned_default_route: true
    web.vm.network :private_network,
      :libvirt__network_name => "net1",
      :libvirt__dhcp_enabled => false,
      :ip => "10.0.0.1",
      :libvirt__forward_mode => "veryisolated"
  end
  config.vm.define :bd do |bd|
    bd.vm.box = "debian/bullseye64"
    bd.vm.hostname = "servidor-bd-roberto"
    bd.vm.synced_folder ".", "/vagrant", disabled: true
    bd.vm.network :private_network,
      :libvirt__network_name => "net1",
      :libvirt__dhcp_enabled => false,
      :ip => "10.0.0.2",
      :libvirt__forward_mode => "veryisolated"
  end
end
```

## Instalación de un CMS PHP en mi servidor local
