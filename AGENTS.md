# AGENTS.md

Web oficial de **VangardRP**, servidor de roleplay western (RedM, 1890). Todo el contenido visible está en español.

## Stack

TanStack Start (React 19, TanStack Router, file-based routing) · Tailwind CSS 4 · TypeScript estricto · Netlify (`@netlify/vite-plugin-tanstack-start`) · Netlify Image CDN.

## Estructura

```
src/
  content/            # TODOS los datos editables del sitio (sin lógica de UI)
    site.ts           # Nombre, DISCORD_URL, menú principal (MAIN_NAV), rutas de marca, cdnImage()
    normativa.ts      # Normativa General transcrita íntegra del PDF oficial (capítulos → secciones → bloques)
    tienda.ts         # CATEGORIES (exactamente 5) y PRODUCTS
    postulaciones.ts  # Convocatorias: status 'abierta' | 'cerrada' y formUrl
    faq.ts            # Preguntas agrupadas; answer: null = pendiente
    lore.ts           # Capítulos del lore (vacío hasta recibir el texto oficial)
  components/layout/  # SiteHeader (menú + panel de botones), SiteFooter, DiscordButton, PageHeader
  components/ui/      # shadcn/ui
  routes/             # index, lore, normativa, informacion, tienda, faq, postulaciones
  styles.css          # Paleta (negro/rojo/plata), fuentes, .text-metal, .panel, animaciones
public/img/           # marca/, owners/, tienda/<categoría>/
```

## Reglas del proyecto (pedidas por el cliente)

- **No inventar datos oficiales**: reglas, precios, enlaces, lore, ventajas VIP, respuestas FAQ. Si falta un dato, usar `null` y la UI lo muestra como «pendiente».
- Usar solo las imágenes proporcionadas por el cliente; no generar ni usar stock.
- El menú principal es exactamente: Inicio, Lore, Normativa, Información, Tienda, FAQ (en ese orden). Postulaciones va en el panel de botones del header junto a Discord, y en el pie.
- No existe botón «Play» y no debe añadirse junto a Discord.
- Discord: `https://discord.gg/xzVmeE7C7a`, siempre en pestaña nueva (`DiscordButton`).
- La normativa se muestra escrita en la web; no reintroducir el visor/enlace de Heyzine.
- No hay formulario de whitelist en este proyecto; no crear uno, ni formularios propios para postulaciones (solo enlaces externos que dará el cliente).
- No añadir pagos, carritos, bases de datos ni paneles de administración.

## Convenciones

- Imágenes siempre vía `cdnImage(src, width)` (Netlify Image CDN, webp).
- Animaciones con las clases `animate-logo-reveal`, `animate-fade-up`; `prefers-reduced-motion` las desactiva globalmente en `styles.css`.
- Títulos: fuente Cinzel (`font-display`), texto: Alegreya Sans. Acabado metálico con `.text-metal`.
- Postulaciones: cerrada → «Postulaciones cerradas»; abierta sin URL válida → «Formulario no disponible».
- La tienda filtra por `?categoria=<id>` en la URL.
- La normativa admite enlaces profundos `/normativa#<id-de-sección>`: abre y desplaza a la sección.
