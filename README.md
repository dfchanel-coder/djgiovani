# DJ Giovani — Sitio web

Landing page de **DJ Giovani & G.Group Sonorizaciones** (Rivera, Uruguay). Sitio 100 % estático desplegado en GitHub Pages.

🔗 **Sitio en vivo:** https://www.djgiovani.com

## Identidad visual

- **Display:** Unbounded — titulares.
- **Texto:** Space Grotesk — cuerpo.
- **Mono/LCD:** Share Tech Mono — etiquetas, tickers y reproductor.
- **Colores:** negro `#050506`, púrpura `#9d00ff`, pink `#ff0055`, verde fósforo `#c8ff00`.
- **Motivos:** vinilo girando, consola con ecualizador reactivo a la música (Web Audio API), tickers de marquesina, secciones numeradas estilo tracklist, grano y cursor neón.

## Estructura

| Ruta | Descripción |
|---|---|
| `index.html` | Página principal (CSS + JS inline). |
| `media/` | Assets optimizados (WebP + fallback JPG, videos H.264, audio). |
| `robots.txt` / `sitemap.xml` | SEO. |
| `CNAME` | Dominio personalizado para GitHub Pages. |

## Desarrollo

```bash
# Servir localmente
python -m http.server 8000
```

### Optimización de assets

- **Imágenes:** WebP (~80 q) con fallback JPG, dimensiones máx. 1920 px.
- **Videos:** H.264 (libx264, `-crf 27`, `-preset slow`, `-movflags +faststart`).
- **Reproductor:** el audio se enruta por un `AnalyserNode`; si el navegador no soporta Web Audio, el ecualizador cae a una animación CSS.

### Deploy

Push a `main` — GitHub Actions / Pages publica automáticamente el branch.

© 2026 DJ Giovani | G.Group Sonorizaciones. Desarrollado por FB Informática.