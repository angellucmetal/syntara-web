# Syntara Web — Contexto del proyecto

Sitio institucional de Syntara (syntara.com.ar): qué hacemos y en qué proyectos estamos trabajando. Desarrollador único: Lucho. Claude escribe los cambios, Lucho los revisa y decide cuándo se publican — mismo modelo de trabajo que los repos hermanos (`C:\Personal\git\surimed`, `3vt`, `suriarq`).

## Stack

- **Una sola página estática:** `index.html` con el CSS inline en `<style>`. Sin framework, sin build, sin dependencias, sin JavaScript.
- **Assets:** `assets/logo.svg` (header) y `assets/icon.svg` (favicon).
- **Fuentes:** Poppins (títulos) e Inter (texto) desde Google Fonts.
- **Hosting:** Vercel, conectado a `github.com/angellucmetal/syntara-web`. **Cada push a `main` se publica en producción** — no hay staging. No hacer push sin que Lucho lo pida.

Para ver el sitio localmente alcanza con abrir `index.html` en el navegador.

## Estructura

```
syntara-web/
├── index.html          # todo el sitio
├── assets/             # logo e ícono
├── docs/
│   ├── projects.md     # catálogo de proyectos: estado, URL, repo, de dónde sale la info
│   └── decisions.md    # decisiones tomadas sobre el sitio
└── .claude/
    ├── agents/site-reviewer.md
    └── skills/
        ├── site-conventions/   # diseño, tono y estructura del HTML
        └── update-projects/    # cómo agregar o actualizar un proyecto
```

## Convenciones críticas

- **Idioma:** español rioplatense con voseo ("Escribinos", "Retomá"), `lang="es-AR"`. Ver skill `site-conventions`.
- **Colores y medidas siempre vía las variables de `:root`** (`--blue`, `--teal`, `--turquoise`, `--green`, `--grad`, etc.). No hardcodear colores nuevos.
- **Mail de contacto:** `contacto@syntara.com.ar`. Aparece en 3 lugares (nav, botón del hero, footer) — si cambia, cambiar los 3.
- **Proyectos:** la fuente de verdad es `docs/projects.md`. Si se agrega o cambia un proyecto en `index.html`, actualizar también ese archivo (skill `update-projects`).
- **Mobile:** todo tiene que verse bien a 375px. El breakpoint existente es `max-width: 760px`.
- **Sin dependencias nuevas** (frameworks, librerías JS, build tools) salvo que Lucho lo pida.

## Referencias

- Manual de marca: `C:\Users\l_ang\OneDrive\Syntara\Manual_de_Marca_Syntara.pdf`
- Material de cada proyecto: `C:\Users\l_ang\OneDrive\Syntara\<Proyecto>\` y los repos hermanos en `C:\Personal\git\`.
