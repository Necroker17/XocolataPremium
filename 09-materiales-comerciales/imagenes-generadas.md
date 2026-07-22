# Imágenes generadas del brochure (21-22 jul 2026)

> Las 20 imágenes (10 por versión) ya están generadas con los prompts de [prompts-brochure-b2b.md](prompts-brochure-b2b.md) y [prompts-brochure-corporativo.md](prompts-brochure-corporativo.md). Archivos binarios — **no versionados en git**, siguiendo la convención del repo (ver [CLAUDE.md](../CLAUDE.md)).

## Dónde están

`Material grafico/brochure-generado/`
- `b2b/` — 10 paneles, prefijo `xoc-b2b-panel-01` a `xoc-b2b-panel-10`.
- `corporativo/` — 10 paneles, prefijo `xoc-corp-panel-01` a `xoc-corp-panel-10`.

## Panel 10 — "Visión a futuro: insumos y materias primas" (agregado 22 jul)

Tras revisión del equipo se detectó que la línea de insumos ([ver línea de insumos y materias primas](../02-producto/linea-insumos-materias-primas.md)) había quedado fuera de ambas versiones del brochure. Se agregó un panel 10 a cada una, generado en la misma conversación de ChatGPT que el resto de paneles de su versión (para mantener consistencia visual):
- `xoc-b2b-panel-10-insumos.png` — tono directo/comercial, con cinta "VISIÓN A FUTURO" para no vender algo que no es oferta activa hoy. Se inserta después del panel 03 al maquetar.
- `xoc-corp-panel-10-insumos.png` — tono narrativo/institucional, mismo grid de 4 categorías. Se inserta después del panel 05 al maquetar.

Ambos salieron bien a la primera generación.

También quedó una copia en `Descargas\Brushure\` (carpeta de descargas de Chrome) — la copia de trabajo en `Material grafico` es la canónica para el proyecto.

## Cómo se generaron

Con ChatGPT (generación de imágenes nativa), pegando cada prompt de los dos archivos de prompts, uno por uno, en la misma conversación por versión (para mantener consistencia visual entre paneles de una misma pieza). Se usó el navegador para automatizar el proceso y descargar cada imagen generada.

**Nota de calidad:** el Panel 07 corporativo ("Nuestros Clientes") falló en el primer intento ("No se ha podido generar la imagen") — se reintentó con el botón "Inténtalo de nuevo" de ChatGPT y la segunda generación fue exitosa. El resto generó a la primera.

## Correcciones aplicadas antes de generar

Antes de generar, se corrigieron dos cosas en los prompts que hubieran quedado mal si se generaban tal cual:
1. El relleno del Buñuelo ya decía "arequipe o queso" (correcto, corregido en sesión previa).
2. Se quitó el número de WhatsApp `+57 301 165 1177` del panel de contraportada de ambas versiones — no estaba confirmado y no debía imprimirse un dato falso (ver [decisiones abiertas](../decisiones-abiertas.md)).

## Siguiente paso

- Revisar las 18 imágenes y elegir cuáles se usan tal cual vs. cuáles necesitan un segundo pase (texto que se vea recortado, ícono que no cuadre, etc. — normal en generación de imágenes con texto).
- Maquetar el brochure final (tríptico o carrusel) uniendo los 9 paneles de la versión elegida, o ambas si se van a usar en paralelo.
- Cuando se confirme el número de WhatsApp real, regenerar solo el Panel 09 de cada versión con el dato correcto (o agregarlo en edición/Photoshop en vez de regenerar todo).

Ver también [brief-brochure.md](brief-brochure.md).
