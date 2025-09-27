# CV JSON

## JSONRESUME

Estado: En edición. Incompleto (2025-09-07)

- Fuente [JSON](./jsonresume.json)
- Fuente GIST en <https://gist.github.com/diegosc78/>
- Visible en <https://registry.jsonresume.org/diegosc78>
- Editor visual web en <https://registry.jsonresume.org/editor>

## RXRESU.ME

- Fuente [JSON](./reactive_resume.json)
- Visible en <https://rxresu.me/diego.souto/diego-souto-catoira>
- Editor visual web en <https://rxresu.me/dashboard/resumes>
- Instrucciones de publicación en <https://docs.rxresu.me/product-guides/making-your-resume-publicly-available>

## JEKILL AL-FOLIO

- Partiendo de versión [0.14.6](https://github.com/alshedivat/al-folio/tree/v0.14.6)
- Instrucciones en video en <https://github.com/alshedivat/al-folio/blob/v0.14.6/assets/video/tutorial_al_folio.mp4>
- Mi repo en <https://github.com/diegosc78/diegosouto.github.io>
  - Importante: en _config.yaml está la URL (debe coincidir con nombre DNS y protocolo con el que se accederá)
- Cuando se hace push a mi repo se desencadena github actions que compila y publica en rama gh-pages
- Lo de la rama gh-pages es html estático y se puede descargar y montar directamente en nginx. Ejemplo:

```bash
podman run --name alfolio --rm -v ./site:/usr/share/nginx/html:ro -p 8080:80 docker.io/library/nginx:latest
```

## CV HUGO

IMPORTANTE: (2025-09) Ya han cambiado hugo y wowchemy otra vez... es un coñazo... olvidar actualizar. Esto se mantiene únicamente en el devcontainer (versiones congeladas).

### REFERENCIAS

- Hugo <https://gohugo.io/>
- Theme "academic" <https://github.com/wowchemy/starter-hugo-academic>
- Devcontainer GO <https://github.com/microsoft/vscode-remote-try-go/blob/main/.devcontainer/devcontainer.json>
  - Ver tags en <https://mcr.microsoft.com/v2/vscode/devcontainers/go/tags/list>
- Icon packs <https://github.com/FortAwesome/Font-Awesome/tree/5.15.3/svgs/brands>
- Compatibilidad versiones hugo con wowchemy themes <https://github.com/wowchemy/wowchemy-hugo-themes/releases>
- Herramienta PNG to SVG <https://svgtrace.com/png-to-svg>

### REQUISITOS PREVIOS

- Tener instalado hugo-extended y nodejs:
  - En el .devcontainer/Dockerfile puede verse cómo se está haciendo
  - Ojo la versión de paquetería ubuntu es vieja
- Ojo con la matriz de compatibilidad de versiones de hugo y la plantilla wowlchemy (véase <https://github.com/wowchemy/wowchemy-hugo-themes/releases>)

### ESTRUCTURA

- hugo24:
  - config/_default : parámetros generales
  - content : las distintas secciones del CV en sí
  - static/media : el CV en PDF
  - assets/media : logos organizaciones (icons/brands/org-xxx.svg), favicon (icon.png)

### PASOS SEGUIDOS INICIALMENTE EN LA PERSONALIZACIÓN

- config: tuneada configuración general en config/_default
- i18n: incorporada carpeta i18n y modificados languages.yaml y config.yaml siguiendo instrucciones de <https://gohugo.io/content-management/multilingual/>
- rel links: incorporados atributos "id" en todos los bloques de content/_index.md
- quitar ejemplos: incorporados atributos draft=true en los ejemplos (otros fueron directamente borrados).
- assets: tuneados logos organizaciones y favicon en assets/media
- mis datos: pesonalizado en content/authors (avatar, datos)
- secciones: personalizadas secciones en content/_index.md
  - Trayectoria: ojo iconos svg "org-xxx.svg" en icons/brands/
  - Skills: ojo iconos en fas/fab (vienen de fontawesome)
  - Acomplishments: ojo formato svg y nombrado de organizacion en icons/brands/ (véase <https://wowchemy.com/blocks/accomplishments/>)
- privacidad y términos: personalizados textos en content/privacy.md y terms.md
- contenidos en sí:
  - Porfolio proyectos en "content/project/"
  - Formación recibida en "content/publication/"
  - Formación impartida en "content/event/"
  - Artículos en "content/post/"

### LANZAR EN LOCAL PARA VER

```bash
curriculumweb/hugo24$ make devserve
```

La primera vez se intentará descargar módulos (fundamentalmente el theme). Ojo porque en 2023 parece he perdido compatibilidad hacia atrás y he tenido que descargarme el starter desde cero otra vez (<https://github.com/wowchemy/starter-hugo-academic>)

El navegador, mejor abrirlo en ventana privada (a veces en ventana normal se queda tonto cargando cosas de la CDN)

### GENERAR VERSIÓN ESTÁTICA

```bash
curriculumweb/hugo24$ make build
```

### PUBLICAR

La última versión del helm chart cvweb ya tira de git (rama "pro"). Así pues, lo que hay es que dejar en la rama "pro" el contenido del directorio "public".

### ACTUALIZACIONES DE LA BASE DE HUGO

- Descargar el ZIP de la versión de [cv-academic-theme del github](https://github.com/wowchemy/starter-hugo-academic) (véase <https://docs.hugoblox.com/getting-started/install-hugo/>). El enlace directo a la rama main sería <https://github.com/HugoBlox/theme-academic-cv/archive/main.zip>
- Comprobar la versión a la que queremos saltar basándonos en la matriz de compatibilidad. Comprobar:
  - Hugo (ver fichero [netlify.toml](./hugo24/netlify.toml) de la plantilla wowchemy)
  - Go (ver [Dockerfile del hugo](https://github.com/gohugoio/hugo/blob/master/Dockerfile) en cuestión)
  - Node (pillar la LTS en vigor; buscar en google "node lts")
- Modifica el .devcontainer/Dockerfile con las versiones que procedan. Rebuild y re-abrir proyecto en vscode
- Trasladar el Makefile de la carpeta anterior a la nueva y probar a levantar la versión por defecto.
- Pararlo y empezar a trasladar todos los contenidos de la anterior carpeta a la nueva:

```bash
cp -dpR hugo2310/assets/media/icons hugo24/assets/media/
cp -dpR hugo2310/assets/media/icon.png hugo24/assets/media/
rm hugo24/static/uploads/resume.pdf 
cp hugo2310/static/uploads/CV_DiegoSoutoCatoira.pdf hugo24/static/uploads/
cp -dpR hugo2310/i18n hugo24/
```

- A partir de estas copias... lo demás hay que ir comparándolo con diff en el vscode para adaptarse. Previsiblemente las carpetas "config" y "content".

### TO DO

- ARTÍCULOS: Crear algún post al estilo unpocodejava; por ejemplo...
  - CI/CD
  - DEMML
- REPO:
  - (en curso) Crear Makefile (ojo comandos hugo bien montados con parámetros completos)
- I18N:
  - Meter todo también en inglés
