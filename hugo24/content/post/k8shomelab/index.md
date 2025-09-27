---
title: Laboratorio casero de Kubernetes
subtitle: Un pequeño ejemplo de cómo conseguir un entorno de despliegue robusto y de bajo coste para casa

# Summary for listings and search engines
summary: Un ejemplo de un cluster kubernetes multi-arquitectura de bajo coste para alojar aplicaciones en casa

# Link this post with a project
projects: []

# Date published
date: '2023-10-01T00:00:00Z'

# Date updated
lastmod: '2023-10-01T00:00:00Z'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: true

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Durante últimas pruebas de resiliencia (rock64 desconectada)'
  focal_point: ''
  placement: 2
  preview_only: false

authors:
  - admin

tags:
  - Contenedores

categories:
  - Contenedores
---

## Características

- Resiliencia. Aguanta caídas de nodos o aplicaciones, reiniciándose o moviendo cargas a otros nodos
- Escalabilidad. Tanto física (añadir más nodos) como lógica (añadir más réplicas, productos, ...)
- Observabilidad. Métricas hardware, infra y software.

## Hardware

En mi caso:

- 1 raspberry 4GB
- 2 raspberry 8GB
- 1 rock64 4GB
- 1 intel celeron 5000
- 1 intel celeron n100
- 2 SSDs
- Switch 8 puertos, cables, envolventes, ...
- 1 SAI

## Software

En mi caso, entre otras cosas:

- Web personal
- Servidor de música
- Servidor de fotos
- Domótica de casa
- Videovigilancia
- Ingesta de datos (scrappers, rpa, conectores servicios web externos, ...)
- Mensajería asíncrona (bus de eventos usado por ingesta, domótica, alertas, monitorización)
- Alertas (mail, telegram, ...)
- Infra software: registry, monitorización, dns filtrado, balanceador, ...

## Principales retos

- Multi-arquitectura. No todo está preparado para esto. Se han requerido varias adaptaciones para acomodar nodos intel y arm en el mismo cluster.

## Principales limitaciones

- Hay puntos únicos de fallo; por ejemplo, un nodo tiene un dongle USB Zwave. Eso limita las poisibilidades de redespliegue en caliente en otro nodo.
- Potencia. No se le pueden pedir milagros a las raspberries, ni en CPU ni en memoria.
- Almacenamiento distribuido. Algún repositorio es masivo y no puede ser distribuido (con los recursos hardware que tengo).
