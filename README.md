# Sitio Markdown para GitHub Pages

Este directorio contiene un sitio basado en **Markdown** que GitHub Pages publica automáticamente usando **Jekyll** y el tema `jekyll-theme-cayman`.

## Estructura

- `_config.yml`: configuración del sitio y tema.
- `index.md`: página principal en Markdown.
- `404.html`: página 404 con front matter.

## Escribir contenido en Markdown

Para crear nuevas páginas, añade archivos `.md` con cabecera YAML al inicio:

```markdown
---
layout: default
title: Acerca de
---

# Acerca de
Contenido en **Markdown**.
```

Enlázalas desde otras páginas: `[Acerca de](/about)` si el archivo se llama `about.md`.

## Publicar en GitHub Pages

### Con CLI de GitHub (`gh`)

```zsh
# Autenticación (si aplica)
gh auth login

# Sitio de usuario (https://TU_USUARIO.github.io/)
cd "/Users/jamal/Research-Production/Proyecto Pi-GANs/web"
# Reemplaza <TU_USUARIO>
gh repo create <TU_USUARIO>/<TU_USUARIO>.github.io --public --source . --remote origin --push

# Sitio de proyecto (https://TU_USUARIO.github.io/NOMBRE_DEL_REPO/)
# Reemplaza <NOMBRE_DEL_REPO>
gh repo create <NOMBRE_DEL_REPO> --public --source . --remote origin --push
```

Después, en GitHub → Settings → Pages:
- Source: `Branch: main`, `Folder: / (root)`.

### Manual con `git`

```zsh
cd "/Users/jamal/Research-Production/Proyecto Pi-GANs/web"

git init
git add .
git commit -m "Inicial: sitio Markdown para GitHub Pages"

git branch -M main
# Reemplaza <TU_USUARIO> y <NOMBRE_DEL_REPO>
git remote add origin https://github.com/<TU_USUARIO>/<NOMBRE_DEL_REPO>.git
git push -u origin main
```

Activa Pages en Settings → Pages como se indicó arriba.

## Dominio personalizado (opcional)

Crea un archivo `CNAME` en la raíz con tu dominio:

```text
www.midominio.com
```

Configura los registros DNS hacia GitHub según la guía oficial.

## Vista previa local (opcional)

Para previsualizar Jekyll localmente necesitas Ruby/Jekyll. Si no lo tienes, confía en el build de GitHub tras el push.

```zsh
# Instalación rápida (puede requerir Xcode Command Line Tools)
# gem install bundler jekyll
# bundle add github-pages
# bundle exec jekyll serve
```

---

¿Quieres que lo publique ahora? Dime tu usuario de GitHub y si prefieres sitio de **usuario** o de **proyecto**.
