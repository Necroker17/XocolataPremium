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

## Fotos de ingredientes / grid de insumos (29 jul 2026)

Las 4 fotos del patrón "grid de insumos" (ver [propuesta de arquitectura inspirada en Ryze](../08-shopify/propuesta-arquitectura-inspirada-ryze.md#4-arquitectura-de-secciones-propuesta), sección 7) ya están generadas con los prompts en [prompts-branding-logo-empaque.md](prompts-branding-logo-empaque.md#fotos-de-ingredientes--grid-de-insumos-patrón-ryze-agregado-22-jul), misma conversación de ChatGPT ("Xocolata Brand") para mantener consistencia visual con el resto del branding.

| # | Archivo (`Material grafico/branding-generado/`) | Qué es |
|---|---|---|
| 9 | `xoc-brand-09-insumo-harinas.png` | Harina de trigo derramándose de un saco de arpillera |
| 10 | `xoc-brand-10-insumo-lacteos.png` | Cuña de queso costeño + bloque de mantequilla |
| 11 | `xoc-brand-11-insumo-rellenos.png` | Arequipe cayendo en hilo desde cuchara de madera |
| 12 | `xoc-brand-12-insumo-empaques.png` | Rollos de film/kraft + bolsa doypack sin imprimir |

Las 4 salieron correctas a la primera generación, sin necesidad de correcciones. Se convirtieron a JPG optimizado (~100-240 KB, 1000×1000) y se copiaron a `xocolata-theme/assets/xoc-insumo-{harinas,lacteos,rellenos,empaques}.jpg` para usarlas en la nueva sección "Nuestra próxima etapa" del home (`sections/xoc-home.liquid`) — grid de 4 tarjetas foto+beneficio corto, mismo patrón que el "6-Mushroom Blend" de Ryze, con nota explícita de que la línea de insumos es visión a largo plazo y no oferta activa hoy (ver [línea de insumos y materias primas](../02-producto/linea-insumos-materias-primas.md)).

## Foto de estilo de vida — mesa de cafetería (30 jul 2026)

Generada con **Higgsfield → GPT Image 2** (no ChatGPT esta vez — ver [rol de Shopify](../08-shopify/build-log.md) para el porqué), usando las fotos reales `xoc-pandebono.jpg` y `xoc-bunuelo.jpg` como referencia de forma/textura para que el modelo no reinterpretara los productos.

| # | Archivo (`Material grafico/branding-generado/`) | Qué es |
|---|---|---|
| 14 | `xoc-brand-14-cafe-mesa.png` | Mesa de cafetería con Pandebono en canasta de mimbre + Buñuelo partido (solo arequipe) + café — luz cálida de mañana, fondo de cafetería desenfocado |

Usada como imagen protagonista (banner 16:9) de la sección "Se sienten en casa" del home, reemplazando el panel anterior de foto pequeña + texto. Versión web optimizada en `xocolata-theme/assets/xoc-cafe-mesa.jpg` (~210 KB, 1600px de ancho).

## Diseño final de empaque (31 jul 2026) — ya no es IA, es el diseño de producción real

`Material grafico/branding-generado/XOCOLATA X4 REF.pdf` — entregado por Daka/diseñadora externa, no generado con IA. Reemplaza toda la "ronda de correcciones v2/v3" de empaques con IA descrita arriba: es el arte final listo para imprimir de los 4 productos (Empanada de Cambray, Almojábana Especial, Buñuelo Relleno, Pandebono en Rosca), 16.75 × 25 cm, frente con ventana transparente + reverso completo (tabla nutricional, ingredientes, instrucciones de preparación, historia de marca, QR, código de barras, sello "Producto Colombiano Premium"). Usa el motivo de ramas doradas (laurel), no el de vapor ni el de espigas de trigo.

Revisado el contenido de ingredientes/alérgenos — ver la corrección importante en [empaques y alérgenos](../02-producto/empaques-y-alergenos.md): la Almojábana Especial sí contiene trigo (no es candidata gluten-free como se asumía antes), y el Pandebono tiene una inconsistencia menor en el uso del calificativo "Pasteurizado".

## Fotos de negocio para prueba social + empaques con producto (30-31 jul 2026)

Generadas con **Higgsfield → GPT Image 2**. Sin rostros de personas (ver [build-log](../08-shopify/build-log.md) para el razonamiento — no se fabrica una identidad falsa para acompañar una cita de ejemplo).

| # | Archivo (`Material grafico/branding-generado/`) | Qué es |
|---|---|---|
| 15 | `xoc-brand-15-testimonio-panaderia.png` | Mostrador de panadería genérico, sin personas ni marcas — thumbnail del testimonio "Panadería El Trigal (ejemplo)" |
| 16 | `xoc-brand-16-testimonio-distribuidora.png` | Bodega de distribución genérica — thumbnail del testimonio "Distribuidora Andina (ejemplo)" |
| 17 | `xoc-brand-17-testimonio-cafe.png` | Mostrador de cafetería genérico — thumbnail del testimonio "Café Latino Express (ejemplo)" |
| 18 | `xoc-brand-18-empaques-producto.png` | Empaque final real (Empanada Cambray + Pandebono Rosca) renderizado en 3D fotorrealista sobre mármol oscuro, con el producto correcto visible en cada ventana — generado usando el PDF de empaque final de Daka y las fotos reales de producto como referencia |

La foto de empaques (#18) reemplaza la imagen genérica de rollos de plástico sin marca que tenía la tarjeta "Empaques y soporte" en el grid de insumos del home — ahora muestra el empaque real de Xocolata. Versión web en `xocolata-theme/assets/xoc-insumo-empaques.jpg` (reemplaza el archivo anterior del mismo nombre).

## Fotos del proceso "Cómo funciona" (31 jul 2026)

Generadas en ChatGPT (conversación "Xocolata Brand"), mismo sistema visual, contando el proceso con el Pandebono en Rosca.

| # | Archivo (`Material grafico/branding-generado/`) | Qué es |
|---|---|---|
| 19 | `xoc-brand-19-paso-recibes.png` | Pandebono congelado, escarcha y niebla fría — paso "Recibes" |
| 20 | `xoc-brand-20-paso-horneas.png` | Pandebono dorándose en el horno, puerta entreabierta — paso "Horneas" |
| 21 | `xoc-brand-21-paso-vendes.png` | Pandebonos horneados en vitrina de panadería — paso "Vendes" |

Versión web en `xocolata-theme/assets/xoc-paso-{01-recibes,02-horneas,03-vendes}.jpg` (~160-206 KB). Cada foto acompaña su paso correspondiente en la sección "Cómo funciona" del home, con el número superpuesto en un badge translúcido.

## Cinemagraph del hero (31 jul)

Generado con Higgsfield (Seedance 2.0, image-to-video) a partir de `xoc-hero.jpg` (ya existente, con vapor pintado de fondo) — misma técnica del cinemagraph del pandebono (sección de nostalgia): cámara fija, el pan no se deforma, solo el vapor de fondo se mueve. 5 segundos, 1920×1080. Verificado frame a frame antes de integrar. Archivo: `xocolata-theme/assets/xoc-hero-cinemagraph.mp4` (~2.6 MB). Reemplaza la foto estática como fondo del hero (`<video autoplay muted loop playsinline>`, con la foto original como `poster`/fallback y respetando `prefers-reduced-motion`).

## Pendiente (decisión del equipo)

- [ ] **Elegir el motivo final** entre vapor dorado (opción 3, recomendada) y laurel (opción 4) — los 4 empaques ya generados usan vapor dorado; si se prefiere laurel, se regeneran los 4 frentes con ese motivo (cambio de una línea en cada prompt).
- [ ] **Terminar la ronda de correcciones de color/perspectiva/cantidad/nombre** en los 4 empaques (ver tabla arriba) — quedó a medias.
- [ ] El **reverso de los 4 empaques** (tabla nutricional, ingredientes, código de barras) no se generó con IA — se recomienda hacerlo en diseño vectorial real una vez Daka confirme la ficha técnica exacta (ver la sección de reverso en el [brief de branding](brief-branding-profesional.md)).
- [ ] Validar con Daka la lista de ingredientes propuesta en el brief antes de imprimir cualquier empaque.

## Foto del hero: empaques reales (31 jul)

| # | Archivo | Descripción |
|---|---|---|
| 22 | `xoc-brand-22-hero-empaques.png` | Empanada de Cambray + Pandebono en Rosca, empaque real, sobre mármol oscuro, formato horizontal para hero |

Generada en ChatGPT (conversación "Xocolata Brand") con el PDF real del empaque (`XOCOLATA X4 REF.pdf`) como referencia, color corregido a `#7A1833`/`#5C1226`/`#A82B4A`. Corrección de textura aplicada en la misma sesión: empanada y pandebono deben verse lisos (masa de yuca/maíz, no trigo), no hojaldrados. Versión web en `xocolata-theme/assets/xoc-hero.jpg`, con cinemagraph de vapor regenerado sobre esta foto (`xoc-hero-cinemagraph.mp4`). Reemplaza la foto de "comida servida" anterior — ver [build log](../08-shopify/build-log.md).

## Foto de cada producto en su empaque individual (31 jul)

| # | Archivo | Descripción |
|---|---|---|
| 23 | `xoc-empanada-empaque.png` | Bolsa de Empanada de Cambray, empaque real, mármol oscuro |
| 24 | `xoc-pandebono-empaque.png` | Bolsa de Pandebono en Rosca, empaque real, mármol oscuro |
| 25 | `xoc-bunuelo-empaque.png` | Bolsa de Buñuelo Relleno, empaque real, mármol oscuro |
| 26 | `xoc-almojabana-empaque.png` | Bolsa de Almojábana Especial, empaque real, mármol oscuro |

Generadas en ChatGPT (conversación "Xocolata Brand") con el PDF real del empaque (`XOCOLATA X4 REF.pdf`) y la foto del hero como referencia, mismo color de marca (`#7A1833`/`#5C1226`/`#A82B4A`). Cada bolsa muestra el producto real a través de la ventana transparente. Versión web en `xocolata-theme/assets/xoc-{empanada,pandebono,bunuelo,almojabana}-empaque.jpg`, insertadas en la sección "Cómo viene tu pedido" de cada página de producto — ver [build log](../08-shopify/build-log.md).

Ver también [brief-branding-profesional.md](brief-branding-profesional.md) e [identidad y posicionamiento](identidad-y-posicionamiento.md).
