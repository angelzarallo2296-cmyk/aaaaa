# VangardRP — Web oficial

Web del servidor de roleplay western **VangardRP** (RedM, universo de Red Dead Redemption 2, ambientado en 1890). Permite consultar el lore, leer la normativa oficial completa, conocer a los Owners, explorar la tienda, ver las postulaciones, resolver dudas en la FAQ y entrar en Discord.

## Tecnologías

- TanStack Start + React 19 + TypeScript
- Tailwind CSS 4 (paleta negro / rojo / plata en `src/styles.css`)
- Netlify (despliegue) y Netlify Image CDN (imágenes optimizadas)

## Ejecutar en local

```bash
pnpm install
netlify dev   # o: pnpm dev
```

## Dónde se edita cada cosa

| Qué | Archivo |
|-----|---------|
| Invitación de Discord, menú, logotipo | `src/content/site.ts` |
| Normativa completa | `src/content/normativa.ts` |
| Productos de la tienda | `src/content/tienda.ts` |
| Convocatorias (estado y enlace del formulario) | `src/content/postulaciones.ts` |
| Preguntas frecuentes | `src/content/faq.ts` |
| Capítulos del lore | `src/content/lore.ts` |
| Owners | `src/routes/informacion.tsx` (constante `OWNERS`) |

## Imágenes

```
public/img/marca/logo-vangardrp.png        Logotipo original
public/img/marca/banner-vangardrp.png      Estandarte (Lore y vista previa al compartir)
public/img/owners/franxu.png               Fotografía de Franxu
public/img/owners/sevvi3.png               Fotografía de Sevvi3
public/img/tienda/casas/casas-nativas.png
public/img/tienda/casas/interiores-sin-mapear.png
public/img/tienda/casas/casas-mapeadas.png
public/img/tienda/caballos/catalogo-1.png … catalogo-7.png
public/img/tienda/peds/peds.png
public/img/tienda/animales/mascotas.png
public/img/tienda/vip/                     (vacía: pendiente de imagen VIP)
```

Para sustituir una imagen, reemplaza el archivo manteniendo el mismo nombre. Para añadir una nueva, guárdala en la carpeta de su categoría y pon su ruta en el campo `image` del producto.

## Contenido pendiente

- Texto del lore oficial.
- Información e imagen del VIP (ventajas, precio, condiciones).
- Precio de los Peds y de los caballos de las láminas V, VI y VII.
- Enlaces y estado real de las convocatorias de Postulaciones.
- Respuesta oficial a «¿Cómo me conecto al servidor?» en la FAQ.
