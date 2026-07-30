# Propuesta: arquitectura de la página inspirada en Ryze Superfoods

> Analizamos [ryzesuperfoods.com](https://www.ryzesuperfoods.com/) a pedido del equipo como referencia de experiencia visual y de UX para elevar la página wholesale. Este documento mapea el modelo de negocio de Ryze, lo compara con el de Xocolata, y propone una arquitectura de secciones que toma prestada la **presentación** de Ryze sin copiar su **motor comercial** — que es fundamentalmente distinto al nuestro. Complementa [brief de la página wholesale](brief-pagina-wholesale-b2b.md) y [rol de Shopify](rol-de-shopify.md).

## Veredicto rápido

**Es viable — pero como fuente de patrones de presentación, no como plantilla de negocio.** Ryze es un e-commerce D2C transaccional de bajo precio unitario y alto volumen; Xocolata es un lead-gen B2B de alto valor por cuenta y ciclo de venta largo. Casi todo lo que hace que la página de Ryze *se vea y se sienta* premium se puede adaptar 1:1. Casi todo lo que hace que Ryze *venda* (carrito, suscripción, afiliados, reseñas masivas) no aplica hoy — y forzarlo diluiría la estrategia de WhatsApp que ya está funcionando. Al final del documento hay un camino para cuando eso cambie.

---

## 1. El modelo de negocio de Ryze (mapeo completo)

| Dimensión | Cómo opera Ryze |
|---|---|
| **A quién le vende** | Consumidor final individual (B2C) — quien toma la decisión de compra es quien va a consumir el producto |
| **Qué vende** | Un solo producto ancla (café de hongos) + línea corta de variantes/bundles, precio bajo-medio ($30-50 USD), apto para compra por impulso |
| **Cómo convierte** | Autoservicio: agrega al carrito, paga con tarjeta, listo — todo en la misma sesión, sin hablar con nadie |
| **Motor de recompra** | Suscripción (Subscribe & Save) — la relación es automática, no depende de una persona dando seguimiento |
| **Motor de confianza** | Escala: 200K+ reseñas, contador de compradores, "verified buyer" — la prueba social funciona por *volumen* |
| **Motor de adquisición** | Ads pagados (Meta/TikTok) hacia landing pages de alta conversión + programa de afiliados/embajadores que amplifica el alcance |
| **Urgencia** | Artificial y recurrente — descuentos por temporada con countdown, siempre hay una "oferta activa" |
| **Ciclo de venta** | Segundos a minutos. Una sesión, una decisión, una persona. |

## 2. El modelo de negocio de Xocolata (mapeo completo)

| Dimensión | Cómo opera Xocolata hoy |
|---|---|
| **A quién le vende** | Negocios — distribuidores, supermercados, food service, panaderías/restaurantes (B2B) — quien decide no es quien consume |
| **Qué vende** | Portafolio de 4 productos, por caja (mínimo 1 caja), precio bajo cotización — no hay "precio de catálogo" público |
| **Cómo convierte** | Conversación: WhatsApp/email → degustación → negociación → primera orden. La página **no vende**, genera el lead. Ver [brief de la página](brief-pagina-wholesale-b2b.md). |
| **Motor de recompra** | Relación comercial directa (hoy manual; Fase 4 contempla un portal de re-orden — ver [rol de Shopify](rol-de-shopify.md)) |
| **Motor de confianza** | Persona a persona: Triple Sello (garantía real, no descuento), degustación en vivo, exclusividad por territorio, respaldo de exportación/FDA |
| **Motor de adquisición** | Base de 40 negocios objetivo contactados directamente + la feria de Miami como evento de cierre — no hay presupuesto de ads masivo todavía |
| **Urgencia** | Real y con fecha fija — la feria (14-16 sep 2026) asigna territorios; quien llega tarde pierde la exclusividad, no es un descuento inventado |
| **Ciclo de venta** | Semanas a meses. Varias personas, varias conversaciones, una cuenta que vale mucho más que una transacción individual. |

## 3. Comparación lado a lado

| | Ryze | Xocolata | ¿Se adapta? |
|---|---|---|---|
| CTA principal | "Try it" → carrito | "Hablemos" → WhatsApp | No — son motores distintos, pero **ambos son de una sola acción clara**, eso sí se copia (ver sección 4) |
| Precio visible | Sí, en el hero | No, bajo cotización | No — decisión ya tomada y correcta (ver [brief](brief-pagina-wholesale-b2b.md#2-el-b2b-nativo-de-shopify-requiere-plan-plus)) |
| Prueba social | Reseñas masivas (200K+) | Degustaciones en vivo, testimonios uno a uno futuros | Parcial — la *forma* (carrusel, foto real, cita) sí; la *escala* no la tenemos ni la necesitamos |
| Urgencia | Descuento de temporada (recurrente, algo artificial) | Feria con fecha fija (real, no se repite) | No copiar el mecanismo, sí copiar la *ejecución visual* (countdown, banda de color) — ya lo tenemos |
| Transparencia de insumos | Grid de ingredientes con foto | Panel "visión a futuro: insumos" (ya construido en el brochure) | **Sí, directo** — incluso ya teníamos el concepto, Ryze mejora la ejecución visual |
| Storytelling de fundador | Ilustración + texto personal | Narrativa de nostalgia ya definida, falta la cara humana | Sí, cuando haya foto real de Marlen |
| FAQ | Acordeón de objeciones de compra individual | Objeciones de compra B2B (mínimos, envíos, certificaciones) | Sí, directo — contenido distinto, mismo patrón UI |
| Afiliados/embajadores | Programa completo | — | No — no existe la figura de "embajador" en un modelo de distribuidores |
| Newsletter de email | Captura genérica | — | No — ya lo evaluamos y compite con el CTA de WhatsApp, se descartó |

---

## 4. Arquitectura de secciones propuesta

Mantiene el orden narrativo ya validado en el [brief de la página](brief-pagina-wholesale-b2b.md#arquitectura-de-la-página-secciones-en-orden) (emoción → producto → riesgo → oportunidad → cierre), pero adopta la *ejecución visual* de Ryze sección por sección.

| # | Sección | Qué existe hoy | Qué se adapta de Ryze | Estado |
|---|---|---|---|---|
| 0 | **Barra de anuncio + ticker sticky** | Ticker existe, solo vive en el hero | Hacerlo **sticky** (fijo arriba al hacer scroll), como el de Ryze | ✅ Construido |
| 1 | **Hero** | Golpe emocional + 2 CTA | Ya tiene la estructura correcta | ✅ Sin cambios |
| 2 | **Nostalgia** | Texto emotivo, sin foto anotada | Agregar foto del producto con **callouts anotados** (flechas + nota sensorial: "Hojaldre de capas visibles", "Contraste dulce-salado") en vez de solo texto | ✅ Construido — foto + cinemagraph en video (29 jul) |
| 3 | **La colección** | Carrusel horizontal + barra de progreso segmentada (recién construido) | Ya adaptado — es la sección que más se parece a Ryze/Zeal en mecánica | ✅ Construido esta sesión |
| 4 | **Cómo funciona** | 3 pasos con número | Agregar fila de atributos con ícono (estilo Ryze: 48mg cafeína, sin gluten...) → nuestra versión: **-18°C · 8 MIN · HUEVO PASTEURIZADO · PRODUCTO COLOMBIANO** | ✅ Construido |
| 5 | **Triple Sello** | 3 bloques de texto | Convertir en badge visual repetible (como el "30-Day Guarantee" de Ryze), que se pueda reusar cerca del CTA final también | ✅ Construido |
| 6 | **Por qué ser aliado** | Grid de 4 textos | Ya tiene la forma correcta (grid de atributos) | ✅ Sin cambios grandes |
| 7 | **Insumos y materias primas** *(nueva, ya existe en brochure)* | Panel con íconos de línea | Rehacer como **grid de ingredientes con foto real** (harina, queso, relleno) — mismo patrón que el "6-Mushroom Blend" de Ryze | ✅ Construido (29 jul) |
| 8 | **Quiénes somos / founder story** | No existe todavía en el home | Bloque con foto real de Marlen + texto personal de "por qué lo hicimos" | 🖼️ Requiere foto (pendiente del b-roll) |
| 9 | **Prueba social** | No existe todavía (sin clientes) | Carrusel de testimonios con foto + "Aliado verificado" — dejar la sección **construida pero vacía/oculta** hasta tener el primer testimonio real post-feria | ✅ Construido con 3 ejemplos marcados "(ejemplo)" (30 jul) — falta cambiar por citas reales |
| 10 | **Countdown a la feria** | Ya construido, con JS vanilla | Ya tiene la ejecución correcta | ✅ Sin cambios |
| 11 | **FAQ** | No existe todavía | Acordeón con las preguntas reales de comprador B2B (mínimos, envíos, certificaciones, cómo se paga) | ✅ Construido |
| 12 | **CTA final** | Ya existe | Agregar el badge de garantía (repetido de la sección 5) junto al botón, como refuerzo de último momento | ✅ Construido |
| — | **Botón flotante persistente** | No existe | CTA "Hablemos" flotante que sigue el scroll, como el "TRY IT" de Ryze — visible en todo momento sin tener que volver arriba | ✅ Construido |
| — | **"Se sienten en casa"** *(nueva, no estaba en esta tabla original)* | No existía | Adapta la sección "Supporting Everyday Wellness" de Ryze (banda de tags de beneficio + panel "Flavor/Feeling") a la narrativa emocional propia: tags "Sabe a casa"/"Nostalgia instantánea" + panel "Sabor/Sensación" con foto real del Buñuelo Relleno | ✅ Construido (30 jul), entre "La colección" y "Cómo funciona" |

**Leyenda:** ✅ ya está bien así · 🔧 se puede construir ahora con lo que ya tenemos · 🖼️ necesita fotos/assets nuevos · 🆕 contenido nuevo por redactar · ⏳ espera datos reales (clientes, testimonios)

---

## 5. Lo que deliberadamente NO se adapta

- **Carrito/checkout como CTA principal** — contradice la decisión ya tomada en el brief: sin LLC constituida, sin precios cerrados, el comprador B2B negocia por WhatsApp, no paga con tarjeta en el sitio.
- **Programa de afiliados/embajadores** — es una figura de creador de contenido B2C; no existe equivalente en un modelo de distribuidores mayoristas.
- **Captura de email tipo newsletter genérico** — ya lo evaluamos: compite con la urgencia del CTA de WhatsApp/degustación y no aporta nada que la conversación directa no dé mejor.
- **Descuentos/ofertas recurrentes con countdown falso** — nuestra urgencia (la feria) es real y no se puede fabricar una nueva cada mes sin sonar falsos.
- **Reseñas a escala (miles)** — no las vamos a tener en mucho tiempo; forzar el patrón visual sin el volumen real se vería vacío o inventado.

---

## 6. Camino a futuro: si se abre un canal transaccional

Vale la pena construir la arquitectura de la sección 4 pensando en que, si algún día Xocolata abre un canal más parecido al de Ryze (ej. una línea de venta directa a panaderías pequeñas para la línea de insumos, gestionada por comisión — ya mencionado como posibilidad en [rol de Shopify](rol-de-shopify.md#a-futuro) — o un futuro B2C de nostalgia para el consumidor final), **la migración sea natural y no una reconstrucción**:

- Las secciones de contenido (colección, insumos, storytelling, FAQ) no cambian — solo cambia qué hace el botón principal.
- El carrusel de "La colección" ya está armado con la mecánica de scroll+progreso que un catálogo transaccional también usaría.
- El punto de cambio sería el CTA: reemplazar `href="mailto:..."` / WhatsApp por un flujo de carrito real — eso ya está aislado en la variable `cta_url` del tema (`sections/xoc-home.liquid`), así que es un cambio de una línea, no de arquitectura.

**Conclusión:** no hay que elegir entre "arquitectura B2B" y "arquitectura estilo Ryze" — la de Ryze es una capa de presentación que funciona *encima* de cualquier motor comercial. Construimos esa capa ahora, con el motor de hoy (WhatsApp), y queda lista para el motor de mañana si llega.

---

## 7. Plan de implementación sugerido

**Ahora mismo (sin assets nuevos, con lo que ya existe):**
1. Ticker sticky — ✅ hecho
2. Botón flotante "Hablemos" — ✅ hecho
3. Fila de atributos con ícono en "Cómo funciona" — ✅ hecho
4. Badge de garantía repetible (Triple Sello) — ✅ hecho
5. FAQ (contenido ya existe disperso, solo falta consolidar y maquetar) — ✅ hecho

**Con las fotos que ya tenemos de branding:**
6. Foto anotada en la sección de nostalgia — ✅ hecho
7. Grid de insumos con foto real de ingredientes — ✅ hecho (29 jul)

**Esperando datos/assets pendientes:**
8. Founder story (foto real de Marlen — b-roll)
9. Prueba social (testimonios — post-feria/post-piloto)

Ver también [brief de la página wholesale](brief-pagina-wholesale-b2b.md), [rol de Shopify](rol-de-shopify.md) y [build log](build-log.md).
