# Coverdrive — Sitio Web

Sitio web del cuarteto de heavy rock/grunge **Coverdrive** (Santiago, Chile), construido con [Quarto](https://quarto.org) como proyecto de tipo `website`.

## Estructura

```
_quarto.yml        # configuración del sitio (navbar, footer, tema)
styles.scss         # tema visual (rojo/blanco/negro, tipografía del logo)
partials/fonts.html # carga de Google Fonts (Anton, Oswald, Inter)
index.qmd           # inicio
repertorio.qmd       # propuesta escénica y setlist
banda.qmd            # integrantes con foto
rider.qmd            # ficha técnica / rider de sonido
contacto.qmd          # redes y contacto
Images/               # fotografías de la banda y logo
Dossier_Coverdrive.pdf # press kit original, descargable desde el sitio
```

## Requisitos

- [Quarto CLI](https://quarto.org/docs/get-started/) instalado (no requiere R para renderizar este sitio, ya que no hay código ejecutable, solo Markdown/HTML).
- Opcional: abrir `Coverdrive.Rproj` en RStudio, que detecta automáticamente el proyecto Quarto.

## Desarrollo local

```bash
quarto preview
```

Esto levanta un servidor local con recarga automática.

## Build

```bash
quarto render
```

El sitio se genera en la carpeta `docs/` (configurado como `output-dir` en `_quarto.yml`).

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub (por ejemplo `coverdrive`) y súbelo:
   ```bash
   git init
   git add .
   git commit -m "Sitio web de Coverdrive"
   git branch -M main
   git remote add origin https://github.com/<tu-usuario>/<tu-repo>.git
   git push -u origin main
   ```
2. En GitHub, ve a **Settings → Pages**.
3. En **Build and deployment → Source**, selecciona **Deploy from a branch**.
4. Elige la rama **main** y la carpeta **/docs**, luego guarda.
5. El sitio quedará disponible en `https://<tu-usuario>.github.io/<tu-repo>/`.
6. (Opcional) Descomenta y completa `site-url` en `_quarto.yml` con esa URL para que las tarjetas de redes sociales (Open Graph/Twitter Card) usen la URL absoluta correcta.

Cada vez que edites el sitio, corre `quarto render` de nuevo y sube los cambios (incluyendo la carpeta `docs/` actualizada) para que se reflejen en GitHub Pages.
