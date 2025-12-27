---
# Leave the homepage title empty to use the site title
title:
date: 2023-10-01
type: landing

sections:
  - block: about.biography
    id: about
    content:
      title: Quién soy
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
  - block: skills
    id: skills
    content:
      title: Competencias
      subtitle: "Competencias personales y técnicas"
      text: ''
      # Choose a user to display skills from (a folder name within `content/authors/`)
      username: admin
    design:
      columns: '1'
  - block: experience
    id: experience
    content:
      title: Trayectoria
      subtitle: Experiencia profesional
      # Date format for experience
      #   Refer to https://docs.hugoblox.com/customization/#date-format
      date_format: Jan 2006
      # Experiences.
      #   Add/remove as many `experience` items below as you like.
      #   Required fields are `title`, `company`, and `date_start`.
      #   Leave `date_end` empty if it's your current employer.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - company: Universidad de A Coruña
          company_url: "https://fic.udc.es/"
          company_logo: org-udc
          date_start: "1996-09-15"
          date_end: "1999-07-01"
          description: |-
            Ingeniería técnica en informática de gestión
          location: A Coruña
          title: Ingeniero técnico
        - company: Level Telecom SL
          company_url: ""
          date_start: "1999-09-15"
          date_end: "2000-03-01"
          description: |-
            Analista-Programador:
            * Consultoría para la implantación de un ERP en sector textil
            * Desarrollo componentes integración EDI
            * Mantenimiento de webs
          location: Santiago
          title: Analista-Programador
        - company: Universidad de A Coruña
          company_url: "https://fic.udc.es/"
          company_logo: org-udc
          date_start: "2000-09-15"
          date_end: "2003-07-01"
          description: |-
            Ingeniería informática
          location: A Coruña
          title: Ingeniero informático
        - company: Universidad de A Coruña
          company_url: "https://fic.udc.es/"
          company_logo: org-udc
          date_start: "2001-12-15"
          date_end: "2002-12-15"
          description: |-
            Becario en Centro de Cálculo y departamento TIC de la Universidad:
            * Instalación y configuración de servidores
            * Mantenimiento de webs
          location: A Coruña
          title: Programador. Técnico de sistemas
        - company: GIG y Centro Gerontológico La Milagrosa
          company_url: "http://gerontologia.udc.es/"
          company_logo: org-milagrosa
          date_start: "2003-06-15"
          date_end: "2004-06-15"
          description: |-
            Jefe de proyecto:
            * Liderazgo proyecto mantenimiento sistema de gestión del Plan Gallego de Inclusión Social
            * Colaboración en proyectos de I+D+i
            * Liderazgo proyecto de desarrollo de gestión expediente clínico gerontológico
          location: A Coruña
          title: Jefe de proyecto
        - company: Altia
          company_url: "https://www.altia.es/"
          company_logo: org-altia
          date_start: "2004-07-01"
          date_end: ""
          description: |-
            Como Analista-Programador y Consultor (desde 2004 hasta 2012):
            * Proyectos de desarrollo y mantenimiento de aplicaciones en tecnologías J2EE
            * Consultoría estratégica de sistemas y de seguridad
            
            Como Jefe de Proyecto y luego Gerente de Proyectos (desde 2010):
            * Gestión proyectos de desarrollo y mantenimiento, fundamentalmente en tecnologías Java
            * Gestión proyectos de integración de sistemas
            * Gestión proyectos de consultoría
            * Gestión proyectos de implantación de soluciones
            * Liderazgo de proyectos de innovación
            * Colaboración en la evolución del modelo de procesos corporativo
            * Colaboración en la implantación y certificaciones de modelos de calidad
            
            Como Responsable de Formación (2012 a 2017):
            * Coordinación de las actividades de formación a nivel global de la compañía
            * Colaboración en la definición de las líneas estratégicas de formación

            Como miembro de la Unidad de Riesgos Globales (2021-):
            * Identificación, evaluación y priorización de riesgos tecnológicos para todas las empresas del Grupo Altia
            * Asesoramiento sobre líneas de acción y seguimiento de planes de acción

            Como Responsable de Estrategia Tecnológica y Partnerships (2023-):
            * Observatorio tecnológico y determinación de la estrategia tecnológica de la compañía
            * Gestión de las relaciones con los partners
            * Establecimiento de la arquitectura y directrices de desarrollo corporativa
            * Liderazgo equipo interno de evaluación de productos
          location: A Coruña
          title: Gerente de proyectos
    design:
      columns: '2'
  - block: accomplishments
    id: functions
    content:
      # Mismas notas y campos utilizables que en la sección de "certificaciones"
      title: 'Funciones'
      subtitle: "Funciones desempeñadas profesionalmente"
      date_format: "2006"
      items:
        - title: Responsable de estrategia tecnológica y partners
          organization: "desde"
          date_start: "2023-01-01"
          date_end: ""
          description:  |-
            Integrado dentro de la Dirección de Tecnología, responsable de:
            * Observatorio tecnológico.
            * Establecimiento de estrategia tecnológica e impulso de acciones.
            * Evaluación de productos y nuevas tecnologías.
            * Definición y evolución de arquitecturas homologadas internamente.
            * Visado técnico de propuestas y proyectos.
            * Gestión de relaciones con los partners.
            * Difusión interna.
          url: ""
        - title: Jefe de proyecto - Gerente de proyectos - Preventas
          organization: "desde"
          date_start: "2010-06-01"
          date_end: ""
          description:  |-
            * Asesoramiento y prescripción de soluciones.
            * Elaboración de propuestas técnicas.
            * Responsable e interlocutor principal ante los clientes en la ejecución.
            * Planificación de proyectos.
            * Liderazgo de equipos.
            * Seguimiento y control.
            * Aseguramiento de la calidad.
            * Validación, aceptación, cierre y retrospectiva.
            * Experiencia con diversas metodologías: predictivas (pmi) y ágiles (scrum).
            * Experiencia en distintas tipologías: desarrollo-mantenimiento, consultoría, implantaciones, soporte, I+D+i.
          url: ""
        - title: Miembro de la unidad de riesgos globales
          organization: "desde"
          date_start: "2020-12-01"
          date_end: ""
          description:  |-
            A nivel de grupo de empresas (perímetro cotización)
            * Seguimiento y análisis de contexto: macro y sectorial.
            * Identificación y valoración de riesgos globales para la organización.
            * Asesoramiento sobre planes de acción.
            * Seguimiento de planes de acción e indicadores sobre los riesgos.
            * Reporte a comisión de auditoría.
          url: ""
        - title: Responsable de varios sistemas corporativos internos
          date_start: "2014-01-01"
          date_end: "2022-12-01"
          description:  |-
            Responsable de múltiples herramientas corporativas: 
            * Plataforma de orquestación: kubernetes
            * CI/CD: jenkins, argocd
            * QA: sonarqube 
            * Repositorios de artefactos: sonatype nexus, harbor.io
            * Análisis de dependencias: dependency-track
            * Análisis y visualización de datos: metabase, talend
            * Inventario TI: snipeit, ocsng
            * eLearning: moodle
            * Cuestionarios: limesurvey
            * CRM: suite crm
            
            Sobre ellas:
            * Selección, configuración, personalización y mejoras.
            * Despliegues, actualizaciones, roadmap.
            * Administración funcional y técnica.
            * Soporte funcional y técnico.                        
          url: ""
        - title: Responsable de formación
          date_start: "2017-01-01"
          date_end: "2012-12-01"
          description:  |-
            * Definición de planes estratégicos anuales para la compañía.
            * Validación de planes operativos y coordinación acciones de las distintas oficinas.
            * Gestión de solicitudes de formación.
            * Organización de acciones formativas.
            * Interlocución con proveedores de formación.
          url: ""
        - title: Auditor interno ISO 9001
          date_start: "2009-01-01"
          date_end: "2017-01-01"
          description:  |-
            * Colaboración en la elaboración y mantenimiento de los procesos, instrucciones técnicas y plantillas corporativas.
            * Auditoría interna de proyectos.
            * Informes de resultados y recomendaciones.
          url: ""
        - title: Consultor
          organization: "desde"
          date_start: "1999-09-01"
          date_end: ""
          description:  |-
            * Análisis de información.
            * Reuniones y entrevistas.
            * Auditorías de situación actual (as-is) y técnicas de seguridad.
            * Planteamiento de situación objetivo (to-be)
            * Elaboración de planes de acción.
            * Definición y establecimiento de procedimientos e instrucciones técnicas.
            * Elaboración de catálogos de servicios TI.
          url: ""
        - title: Analista-Programador
          date_start: "1999-09-01"
          date_end: "2012-06-01"
          description:  |-
            * Captura de requisitos manteniendo interlocución directa con el cliente.
            * Análisis y diseño de sistemas de información.
            * Desarrollo de aplicaciones web full-stack.
            * Coordinación en un equipo de trabajo, control de cambios, ...
            * Pruebas unitarias, de integración, de sistema y colaboración en UATs.
            * Despliegues de aplicaciones.
            * Soporte técnico.
          url: ""
    design:
      columns: '2'
  - block: portfolio
    id: projects
    content:
      title: Proyectos
      subtitle: "Proyectos destacados liderados"
      filters:
        folders:
          - project
      # Default filter index (e.g. 0 corresponds to the first `filter_button` instance below).
      default_button_index: 0
      # Filter toolbar (optional).
      # Add or remove as many filters (`filter_button` instances) as you like.
      # To show all items, set `tag` to "*".
      # To filter by a specific tag, set `tag` to an existing tag name.
      # To remove the toolbar, delete the entire `filter_button` block.
      buttons:
        - name: Todos
          tag: '*'
        - name: Smart cities
          tag: "Smart cities"
        - name: "Admón electrónica"
          tag: "e-Admon"
        - name: "Tarjetas"
          tag: "Smart Cards"
        - name: "GIS"
          tag: "GIS"
        - name: "Analítica de datos"
          tag: "BI"
        - name: "Gestión de activos"
          tag: "GMAO"
        - name: "Interoperabilidad"
          tag: "SOA"
        - name: "Apps web"
          tag: "Apps web"
        - name: "Consultoría"
          tag: "Consultoría"
        - name: "Portales"
          tag: "CMS"
        - name: "Contenedores"
          tag: "Contenedores"
        - name: "Cloud"
          tag: "Cloud"
        - name: "IA"
          tag: "IA generativa"

    design:
      # Choose how many columns the section has. Valid values: '1' or '2'.
      columns: '1'
      view: showcase
      # For Showcase view, flip alternate rows?
      flip_alt_rows: false
  #- block: markdown
  #  content:
  #    title: Galería
  #    subtitle: ''
  #    text: |-
  #      {{< gallery album="demo" >}}
  #  design:
  #    columns: '1'
  - block: accomplishments
    id: accomplishments
    content:
      # Note: `&shy;` is used to add a 'soft' hyphen in a long heading.
      title: 'Certificaciones'
      subtitle: "Certificaciones oficiales"
      # Date format: https://docs.hugoblox.com/customization/#date-format
      date_format: Jan 2006
      # Accomplishments.
      #   Add/remove as many `item` blocks below as you like.
      #   `title`, `organization`, and `date_start` are the required parameters.
      #   Leave other parameters empty if not required.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - certificate_url: https://graphacademy.neo4j.com/c/ab612bf7-0970-4362-8398-63479a9fb7e7/
          date_end: ""
          date_start: "2025-09-05"
          description:  |-
            * Graph Data Modeling
            * Cypher Query language
            * Neo4j with Python
          organization: Graph Academy (Neo4j)
          organization_url: https://neo4j.com/
          title: Neo4j Certified Professional
          url: "https://graphacademy.neo4j.com/c/ab612bf7-0970-4362-8398-63479a9fb7e7/"
        - certificate_url: https://training.stratio.com/admin/tool/lp/plan.php?id=8826
          date_end: ""
          date_start: "2023-11-07"
          description:  |-
            * Plataforma Stratio
            * Augmented Data Governance
            * Entorno analítico Rocket
          organization: Stratio
          organization_url: https://stratio.com/
          title: Stratio Augmented Data Fabric Basics Certification
          url: "https://training.stratio.com/admin/tool/lp/plan.php?id=8826"
        - certificate_url: https://www.youracclaim.com/badges/c8d175ad-1698-4d0d-83c8-2d1d950e7277/public_url
          date_end: ""
          date_start: "2019-04-10"
          description:  |-
            * Blockchain
            * Smart contracts
            * Trabajando con la plataforma Ethereum
            * Desarrollo de DApps
            * Tokenomics
          organization: BlockchainUnited
          organization_url: https://www.blockchain-united.org/
          title: BcU Certified Blockchain Ethereum Professional (CBEP)
          url: "https://www.blockchain-united.org/certification"
        - certificate_url: https://scrummanager.com/index.php/es/perfil-publico?id=27540
          date_end: ""
          date_start: "2019-09-06"
          description:  |-
            * Nivel experto
          organization: ScrumManager
          organization_url: https://scrummanager.com/
          title: Scrum Master
          url: "https://scrummanager.com/website/c/info/academic-framework.php"
        - certificate_url: https://www.pmi.org/certifications/certification-resources/registry
          date_start: "2009-10-10"
          date_end: ""
          title: Project Management Professional (PMP)
          description:  |-
            * Gestión integrada
            * Gestión de alcance, tiempo, costes, calidad, riesgos, ...
            * Gestión de equipos
            * Gestión de comunicaciones e interesados
          organization: "ProjectManagementInstitute"
          organization_url: http://www.pmi.org/
          url: "https://www.pmi.org/certifications/project-management-pmp"
    design:
      columns: '2'
  - block: collection
    id: featured
    content:
      title: Cursos
      subtitle: "Siempre aprendiendo algo nuevo"
      filters:
        folders:
          - publication
        featured_only: false
    design:
      columns: '2'
      view: compact
  - block: collection
    id: talks
    content:
      title: Transmitiendo conocimiento
      subtitle: "Formación impartida: workshops y cursos"
      filters:
        folders:
          - event
      count: 3
    design:
      columns: '2'
      view: compact
  - block: tag_cloud
    content:
      title: Temas
      subtitle: "Pulsa para ver más contenidos"
    design:
      columns: '2'
  - block: collection
    id: posts
    content:
      title: Artículos
      subtitle: 'Posts sobre temas de interés'
      text: ''
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        folders:
          - post
        author: ""
        category: ""
        tag: ""
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ""
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: compact
      columns: '2'
  - block: contact
    id: contact
    content:
      title: Contacto
      subtitle:
      text: |-
        Contacta conmigo para cualquier cosa en la que pueda ayudar. Mejor por correo o por teléfono.
      # Contact (add or remove contact options as necessary)
      email: diego.souto@gmail.com
      phone: (+34) 654598409
      appointment_url: 'https://calendly.com/diegosouto'
      #address:
      #  street: ""
      #  city: Arteixo
      #  region: Coruña
      #  postcode: '15141'
      #  country: España
      #  country_code: ES
      directions: ""
      office_hours: []
      contact_links:
        - icon: linkedin
          icon_pack: fab
          name: LinkedIn
          link: 'https://www.linkedin.com/in/diegosouto'
        - icon: telegram
          icon_pack: fab
          name: Telegram
          link: 'https://telegram.me/@dsoutoc78'
        - icon: skype
          icon_pack: fab
          name: Skype
          link: 'skype:diego_sc_78?call'
        - icon: video
          icon_pack: fas
          name: Zoom
          link: 'https://us05web.zoom.us/j/8523168553?pwd=Bm1YLbzsZTBxZFsvnyiHmUzmHibb6G.1'
      # Automatically link email and phone or display as text?
      autolink: true
      # Email form provider
      form:
        provider: netlify
        formspree:
          id:
        netlify:
          # Enable CAPTCHA challenge to reduce spam?
          captcha: true
    design:
      columns: '2'
---
