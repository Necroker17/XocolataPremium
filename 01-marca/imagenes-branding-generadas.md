# Imágenes generadas del branding profesional (22 jul 2026)

> Las 8 piezas del [brief de branding](brief-branding-profesional.md) ya están generadas con los prompts de [prompts-branding-logo-empaque.md](prompts-branding-logo-empaque.md). Archivos binarios — **no versionados en git**, siguiendo la convención del repo (ver [CLAUDE.md](../CLAUDE.md)).

## Dónde están

`Material grafico/branding-generado/`

| # | Archivo | Qué es |
|---|---|---|
| 1 | `xoc-brand-01-logo-icono.png` | Monograma "X" independiente — favicon/avatar |
| 2 | `xoc-brand-02-logo-fondoclaro.png` | Lockup completo en vinotinto, para fondo claro |
| 3 | `xoc-brand-03-motivo-vapor.png` | Motivo A: vapor dorado (reemplazo de espigas) — **recomendado** |
| 4 | `xoc-brand-04-motivo-laurel.png` | Motivo B: laurel dorado (alternativa) |
| 5 | `xoc-brand-05-empaque-empanada.png` | Frente de empaque — Empanada de Cambray (nuevo, no existía) |
| 6 | `xoc-brand-06-empaque-pandebono.png` | Frente de empaque — Pandebono en Rosca |
| 7 | `xoc-brand-07-empaque-bunuelo.png` | Frente de empaque — Buñuelo Relleno |
| 8 | `xoc-brand-08-empaque-almojabana.png` | Frente de empaque — Almojábana Especial |

También hay copia en `Descargas\Brushure\`.

## Cómo se generaron

Con ChatGPT, mismo método que las imágenes del brochure (ver [imágenes generadas del brochure](../09-materiales-comerciales/imagenes-generadas.md)): una sola conversación para mantener consistencia visual entre las 8 piezas, prompt por prompt, descargando el archivo real de cada generación.

**Nota de calidad:** el empaque de Almojábana generó 2 variantes automáticamente; se eligió la variante 1 (mejor encuadre del producto en la ventana). El resto generó una sola variante y salió bien a la primera.

## Resultado

- El motivo de **vapor dorado** (opción A, la recomendada en el brief) quedó muy logrado — se ve en los 4 empaques flanqueando la ventana, en reemplazo de las espigas de trigo.
- Los 4 empaques mantienen consistencia total: mismo logo, mismo tagline, mismos 3 badges inferiores (Frozen · Producto Colombiano Premium con silueta del país · Ready to Bake), mismo tratamiento de banda con el nombre del producto.
- La **Empanada de Cambray ya tiene empaque propio** — antes no existía ningún diseño para el producto ancla de la campaña.

## Pendiente (decisión del equipo)

- [ ] **Elegir el motivo final** entre vapor dorado (opción 3, recomendada) y laurel (opción 4) — los 4 empaques ya generados usan vapor dorado; si se prefiere laurel, se regeneran los 4 frentes con ese motivo (cambio de una línea en cada prompt).
- [ ] El **reverso de los 4 empaques** (tabla nutricional, ingredientes, código de barras) no se generó con IA — se recomienda hacerlo en diseño vectorial real una vez Daka confirme la ficha técnica exacta (ver la sección de reverso en el [brief de branding](brief-branding-profesional.md)).
- [ ] Validar con Daka la lista de ingredientes propuesta en el brief antes de imprimir cualquier empaque.

Ver también [brief-branding-profesional.md](brief-branding-profesional.md) e [identidad y posicionamiento](identidad-y-posicionamiento.md).
