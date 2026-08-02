# Entrelagos · Plan de lanzamiento del mes

Microsite de una sola página para presentarle al cliente **qué se publica este mes**:

1. **Piezas del mes** — las piezas reales que van a Meta (pauta + orgánico) para captación de leads.
2. **Cronograma** — línea de tiempo semanal coordinando Meta orgánico, Meta pauta y Google Ads.
3. **Google Ads · Keyword research** — grupos de anuncios, concordancias, intención, CPC estimado y negativas.
4. **Contexto** — potencial de valorización, competencia, objetivo y perfil del comprador.

Sitio **100% estático** (HTML + CSS + JS, sin build). Usa el logo oficial del proyecto.

## Estructura
```
entrelagos/
├─ index.html        · toda la app (estilos y JS embebidos)
├─ .nojekyll
├─ README.md
└─ assets/
   ├─ logo.png       · logo oficial (círculo verde)
   ├─ logo-dark.png  · logo sobre fondo claro (respaldo)
   ├─ hero-drone.mp4 · video del hero y de la pieza Reel
   ├─ drone-2.jpg    · poster de video
   └─ post-ig.png    · pieza de Instagram del mes
```

## Cómo subirlo a GitHub Pages (paso a paso)

### Opción A — desde la web, sin comandos (la más fácil)
1. Entra a github.com y haz clic en el **+** arriba a la derecha → **New repository**.
2. Nombre: `entrelagos` · déjalo **Public** · **Create repository**.
3. En el repo vacío haz clic en **“uploading an existing file”**.
4. Arrastra el `index.html`, el `.nojekyll` y **la carpeta `assets/` completa**.
   (Tip: descomprime el .zip primero y arrastra todo el contenido de la carpeta.)
5. Abajo, botón verde **Commit changes**.
6. Ve a **Settings** (rueda dentada del repo) → menú izquierdo **Pages**.
7. En *Build and deployment* → *Source*: **Deploy from a branch**.
   Branch: **main** · carpeta: **/ (root)** · **Save**.
8. Espera 1–2 min y recarga. Arriba aparecerá el link:
   `https://<tu-usuario>.github.io/entrelagos/` — ese es el que le pasas al cliente.

### Opción B — desde la terminal (si ya usas git)
```bash
cd entrelagos
git init
git add .
git commit -m "Entrelagos · plan de lanzamiento del mes"
git branch -M main
git remote add origin https://github.com/<tu-usuario>/entrelagos.git
git push -u origin main
```
Después activa Pages igual que en los pasos 6–8 de la Opción A.

> **Importante:** sube siempre la carpeta `assets/` junto al `index.html`; si falta,
> el logo, el video y la pieza de Instagram no cargan.
> El `.nojekyll` (archivo vacío) evita que GitHub procese el sitio con Jekyll.

## Editar contenido rápido
Todo el contenido vive en objetos JavaScript al inicio del `<script>` en `index.html`:
- `TIMELINE` — las 4 semanas del cronograma
- `KW` — grupos de keywords de Google Ads · `NEGS` — palabras negativas
- `COMP` — tarjetas de competencia
- `ventas` / `pauta` — series de la gráfica

Colores y tipografías en las variables CSS `:root` (paleta de marca `#4f7238`, `#293922`, `#211e1f`, `#ebebac`).
