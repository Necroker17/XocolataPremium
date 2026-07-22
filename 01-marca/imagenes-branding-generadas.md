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

Adicionalmente, de la ronda de correcciones del 22 jul (ver más abajo, quedó incompleta): `xoc-brand-05b-empaque-empanada-v2.png`, `xoc-brand-05c-empaque-empanada-v3.png`, `xoc-brand-06b-empaque-pandebono-v2.png`, `xoc-brand-07b-empaque-bunuelo-v2.png`.

También hay copia en `Descargas\Brushure\`.

## Cómo se generaron

Con ChatGPT, mismo método que las imágenes del brochure (ver [imágenes generadas del brochure](../09-materiales-comerciales/imagenes-generadas.md)): una sola conversación para mantener consistencia visual entre las 8 piezas, prompt por prompt, descargando el archivo real de cada generación.

**Nota de calidad:** el empaque de Almojábana generó 2 variantes automáticamente; se eligió la variante 1 (mejor encuadre del producto en la ventana). El resto generó una sola variante y salió bien a la primera.

## Resultado

- El motivo de **vapor dorado** (opción A, la recomendada en el brief) quedó muy logrado — se ve en los 4 empaques flanqueando la ventana, en reemplazo de las espigas de trigo.
- Los 4 empaques mantienen consistencia total: mismo logo, mismo tagline, mismos 3 badges inferiores (Frozen · Producto Colombiano Premium con silueta del país · Ready to Bake), mismo tratamiento de banda con el nombre del producto.
- La **Empanada de Cambray ya tiene empaque propio** — antes no existía ningún diseño para el producto ancla de la campaña.

## Ronda de correcciones de empaque (22 jul) — estado real, quedó incompleta

Tras revisar los 4 frentes, el equipo pidió 2 rondas de correcciones (ver [brief de branding](brief-branding-profesional.md)): 1) ventana con efecto de plástico transparente real en vez de foto pegada plana, 2) nombre del producto sin banda dorada de fondo. Una tercera ronda ajustó además la perspectiva del producto (piezas completas apiladas, no en corte), la cantidad/tamaño de bolsa según el contenido real, y el color exacto de la bolsa (se midió la referencia original y se validó un tono intermedio `#7A1833`, ver el brief). **El equipo decidió dejar el proceso aquí por ahora** — no se completó el mismo nivel de corrección en los 4 productos. Estado real por producto:

| Producto | Versión más reciente disponible | Qué le falta frente al ideal |
|---|---|---|
| Empanada de Cambray | `xoc-brand-05c-empaque-empanada-v3.png` | Tiene ventana transparente, perspectiva de producto real apilado, cantidad (20 uds) y nombre discreto — pero el color de la bolsa quedó más oscuro de lo validado (`#7A1833` no se aplicó a esta versión). |
| Pandebono en Rosca | `xoc-brand-06b-empaque-pandebono-v2.png` | Solo tiene la corrección de ventana transparente. La versión con perspectiva/cantidad/nombre discreto y color `#7A1833` sí se generó y se confirmó visualmente correcta, pero **el archivo se perdió al descargarlo** (no quedó guardado en ningún lado) y no se volvió a intentar. |
| Buñuelo Relleno | `xoc-brand-07b-empaque-bunuelo-v2.png` | Solo tiene la corrección de ventana transparente. No llegó a la ronda de perspectiva/cantidad/nombre/color. |
| Almojábana Especial | `xoc-brand-08-empaque-almojabana.png` (v1, sin ninguna corrección) | La versión con ventana transparente se generó y se vio correcta, pero no se descargó a tiempo. No llegó a la ronda de perspectiva/cantidad/nombre/color. |

**Si se retoma esta ronda**, los prompts ya están listos en [prompts-branding-logo-empaque.md](prompts-branding-logo-empaque.md) (sección "Corrección v3") — usar siempre el color `#7A1833` (sombras `#5C1226`, luces `#A82B4A`) explícito en el prompt, confirmado como el tono correcto tras medir la referencia original.

## Pendiente (decisión del equipo)

- [ ] **Elegir el motivo final** entre vapor dorado (opción 3, recomendada) y laurel (opción 4) — los 4 empaques ya generados usan vapor dorado; si se prefiere laurel, se regeneran los 4 frentes con ese motivo (cambio de una línea en cada prompt).
- [ ] **Terminar la ronda de correcciones de color/perspectiva/cantidad/nombre** en los 4 empaques (ver tabla arriba) — quedó a medias.
- [ ] El **reverso de los 4 empaques** (tabla nutricional, ingredientes, código de barras) no se generó con IA — se recomienda hacerlo en diseño vectorial real una vez Daka confirme la ficha técnica exacta (ver la sección de reverso en el [brief de branding](brief-branding-profesional.md)).
- [ ] Validar con Daka la lista de ingredientes propuesta en el brief antes de imprimir cualquier empaque.

Ver también [brief-branding-profesional.md](brief-branding-profesional.md) e [identidad y posicionamiento](identidad-y-posicionamiento.md).
