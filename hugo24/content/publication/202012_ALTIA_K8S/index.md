---
title: "Kubernetes. Automatización, escalado y administración de aplicaciones en contenedores"
authors:
- admin
date: "2020-11-30T00:00:00Z"
doi: ""
draft: false

# Schedule page publish date (NOT publication's date).
publishDate: "2020-11-30T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: []

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: "K8S"

abstract: Kubernetes. Automatización, escalado y administración de aplicaciones en contenedores

# Summary. An optional shortened abstract.
summary: Kubernetes. Automatización, escalado y administración de aplicaciones en contenedores - ALTIA - 2020

tags:
- DevOps
- Contenedores
featured: false

links: []
url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: ''
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

## Datos del curso

* Organismo: Altia
* Fecha: 2020-12
* Duración: 25h
* Modalidad: telepresencial
* Diploma acreditativo: disponible

## Temario

SESIÓN 1. INTRODUCCIÓN

* Presentación del curso
* Contexto y origen histórico
* Virtualización vs. Paravirtualización. Origen y base tecnológica de los contenedores
* Qué es docker. Conceptos clave. Ciclos de vida
* Instalación y comandos básicos
* Registry y dockerhub
* Dockerfiles y proceso de construcción-publicación de imágenes
* Redes de contenedores y docker-compose (y buenas prácticas)
* Introducción a la orquestación: docker-swarm y kubernetes
* Conclusiones. Para qué puede servirnos
* Taller práctico solo con docker: frontal web + servidor apps + bd

SESIÓN 2. CONCEPTOS BÁSICOS K8S

* Qué es y para qué sirve
* Arquitectura y componentes
* Cómo funciona internamente
* Aplicabilidades: para qué es apropiado y para qué no
* Tipos de objetos K8S y sus relaciones: pods, deployments, statefulset, service, ingress, namespaces, ...
* Creación de descriptores yaml básicos: specs, probes, semejanza con docker-compose,...
* Etiquetas, selectores y anotaciones
* Instalación para pruebas (minikube / microk8s)
* Conexión a un cluster K8S y comandos básicos en cli: get, apply, ...
* Réplicas y escalado
* Flujo previsto para versionado y actualizaciones sin pérdida de servicio
* Taller práctico: Desplegando y jugando con una app sencilla (pe. apache/nginx)

SESIÓN 3. DESCRIPTORES YAML CON MÁS DETALLE

* Configuración: ConfigMaps y Secrets. Ficheros, envs, certificados
* Despliegues: Deployments y StatefulSets. Probes, requests y limits, afinidades y tolerancias ...
* Persistencia: PersistenVolumes, Claims, StorageClass. Tipos de provisionadores.
* Redes: Services e Ingress-nginx
* Otros: CronJobs
* Mejores prácticas y errores comunes a evitar
* Helm charts
* Herramientas de trabajo más cómodo: vscode+icepanel...
* Taller práctico: Instalar un helm chart

SESIÓN 4. Instalación, configuración y administración básica

* Taller práctico: Instalación y configuración de un cluster real incl dashboard, ingress, helm
* Monitorización: prometheus / ELK
* Lens
* Certificados: cert-manager y letsencrypt
* Registry privado seguro
* Automatización del escalado
* Integración continua: del git a K8S
* Recomendaciones para backups
* Fallos comunes. Troubleshooting.

SESIÓN 5. Prácticas finales

* Taller práctico: Desde el dockerfile al helm chart para una app de ejemplo que tenga un poco de todo: config, almacenamiento, ingress https, un cron
