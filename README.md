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
- Editor visual web en <https://rxresu.me/dashboard/resumes> (autenticarse con github)
- Instrucciones de publicación en <https://docs.rxresu.me/product-guides/making-your-resume-publicly-available>
- Últimamente estoy bajando el PDF de ahí en lugar de generarlo desde el ODT.
  - En el editor visual web, opción generar PDF.
  - A veces no incluye bien la foto. Probar pequeños cambios en CV y reintentar.

## CV HUGO

**IMPORTANTE:** (2025-09) Ya han cambiado hugo y wowchemy otra vez... es un coñazo... olvidar actualizar. Esto **se mantiene únicamente en el devcontainer** (versiones congeladas).

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

Ojo, hacerlo siempre dentro de devcontainer para asegurar versiones exactas prefijadas.

```bash
curriculumweb/hugo24$ make build
```

### PUBLICAR

ANTES 202512:
  - El helm chart cvweb ya tira de git (rama "pro"). Así pues, lo que hay es que dejar en la rama "pro" el contenido del directorio "public".
  - Se publica en infra propia, bajo ddns diegosouto.duckdns.org

TRAS 202512:
  - El contenido de la carpeta hugo24/public/ es el HTML estático generado por HUGO para publicar (tras generar versión estática).
  - Bitnami ya no da soporte a sus imágenes así que volvemos al viejo sistema de tener una imagen propia. Ahora tiramos de helm-parent.
  - El target dockerbuild en el Makefile debe ejecutarse FUERA del devcontainer cuando ya se hizo el make build. El Dockefile tira de dhi.io . Hay que autenticarse previamente (docker login dhi.io) con las credenciales de ponte124 (dockerhub)
  - Se publica en github pages. https://diegosc78.github.io
  - Cuando se hace push a mi repo (rama gh-pages) se desencadena en unos minutos la publicación en gh-pages
  
OPCIONAL (no lo tengo ahora debido a los fallos de disponibilidad intermitentes del ddns duckdns):
  - Se puede aprovechar el nombre diegosouto.duckdns.org para apuntar a la IP de GH Pages y que sirva lo de diegosc78.github.io.

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

## JEKILL AL-FOLIO (experimento)

- Partiendo de versión [0.14.6](https://github.com/alshedivat/al-folio/tree/v0.14.6)
- Instrucciones en video en <https://github.com/alshedivat/al-folio/blob/v0.14.6/assets/video/tutorial_al_folio.mp4>


### TO DO

- ARTÍCULOS: Crear algún post al estilo unpocodejava; por ejemplo...
  - CI/CD
  - DEMML
  - Kit multimedia casa
- I18N:
  - Meter todo también en inglés
