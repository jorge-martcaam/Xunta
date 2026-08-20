# Xunta

Análise da situación actual segundo fontes oficiais da Xunta.

Artículos escritos en [Obsidian](https://obsidian.md/) y publicados como sitio HTML con [Quartz](https://quartz.jzhao.xyz/), vía GitHub Pages.

## Estructura

- `content/` — el vault de Obsidian. Ábrelo como carpeta de vault en Obsidian. Cada subcarpeta es un tema.
  - `content/topic-a/`, `content/topic-b/` — temas placeholder, renómbralos por los temas reales.
- `quartz.config.yaml` — configuración del sitio (título, tema visual, plugins).
- `quartz/` — el motor de Quartz (no tocar salvo que sepas lo que haces).
- `.github/workflows/deploy.yml` — build y despliegue a GitHub Pages en cada push a `production`.

## Ramas

- **`development`** — rama de trabajo por defecto. Escribe y guarda aquí.
- **`production`** — rama de publicación. Solo recibe merges desde `development` cuando un artículo está listo. Cada push aquí dispara el despliegue.

## Primeros pasos (una sola vez, en esta máquina)

1. Instala [Node.js 22+](https://nodejs.org/) (no estaba instalado al crear este repo).
2. `npm ci`
3. `npx quartz plugin install` — instala los plugins listados en `quartz.config.yaml` y genera `quartz.lock.json` (comételo).
4. `npx quartz build --serve` — previsualiza el sitio en local.
5. Abre `content/` como vault en Obsidian y empieza a escribir.
6. En GitHub: Settings → Pages → Source → "GitHub Actions".

## Publicar un artículo

1. Escribe en `development`.
2. Cuando esté listo, PR/merge `development` → `production`.
3. El push a `production` construye y publica en `https://jorge-martcaam.github.io/Xunta/`.
