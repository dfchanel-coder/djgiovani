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
| `robots.txt` / `sitemap.xml` / `llms.txt` | SEO (crawlers clásicos + motores de IA tipo ChatGPT). |
| `CNAME` | Dominio personalizado para GitHub Pages. |

## SEO local

Posicionamiento para búsquedas como "dj en rivera", "discoteca en rivera" o "dj para 15 en Rivera":

- **Contenido:** sección de servicios y FAQ con las frases que usa la gente, escritas de forma natural.
- **Datos estructurados:** `EntertainmentBusiness` (con `geo`, `areaServed` y catálogo de servicios) + `FAQPage`.
- **`llms.txt`:** resumen legible para motores de IA (ChatGPT, Gemini, Perplexity).
- **Verificación:** registrá propiedades en [Google Search Console](https://search.google.com/search-console) y [Bing Webmaster](https://www.bing.com/webmasters) usando `media/favicon.png` o verificación por DNS.

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