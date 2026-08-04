# Checklist de cierre — bloque de construcción en Shopify

> Lista viva de lo que falta para considerar **cerrado** el bloque de Shopify (no el proyecto completo — solo el sitio). Generada el 3 de agosto de 2026 a partir de lo documentado en [build-log.md](build-log.md), [decisiones abiertas](../decisiones-abiertas.md) y [roadmap.md](../roadmap.md). Marcar `- [x]` a medida que se resuelva cada punto.

## Contenido comercial — bloquea CTAs reales en todo el sitio

- [ ] **Número de WhatsApp comercial.** Sigue sin confirmar en ningún documento fuente. Todos los botones "Hablemos" usan `mailto:xocolatapremium@gmail.com` como placeholder (unificado el 4 ago — antes había dos correos distintos en el sitio). Es el pendiente que más se repite en todo el registro del proyecto — no inventar el número, pedirlo directo al equipo.
- [ ] **Mercado EE. UU. en USD.** La tienda hoy solo muestra precios en COP. Para un visitante en Estados Unidos conviene activar visualización en USD (mercado "Estados Unidos"), sin activar checkout con tarjeta mientras la LLC siga en trámite.
- [ ] **Traducción EN a nivel de producto.** El home y la sección "Nuestra Historia" son bilingües, pero las descripciones de los 4 productos en el panel de Shopify (Admin) siguen solo en español.

## Contenido honesto pendiente de reemplazar

- [ ] **3 testimonios reales.** Hoy son ejemplos ilustrativos, marcados explícitamente como "(ejemplo)" en la sección de prueba social. Se reemplazan cuando haya clientes reales del piloto "Primeros 10", después de la feria de Miami.
- [ ] **Founder story.** La sección "Nuestra Historia" del home es institucional por decisión explícita del equipo (no se nombra a la fundadora). Falta decidir si en algún momento se agrega su nombre y una foto real.

## Consistencia de datos con la maquiladora (Daka)

- [x] **Peso real de la Empanada de Cambray.** ✅ Resuelto (3 ago): 80 g es el correcto (coincide con el panel nutricional impreso en el empaque final). Corregido en todo el sitio — carrusel, stat card y panel nutricional de la página de producto.
- [ ] **Certificación gluten free.** Sin validar todavía con Daka qué productos pueden certificarse. Si cambia, hay que actualizar la sección de alérgenos de las páginas de producto correspondientes.

## Decisión de plataforma (no bloquea el cierre, pero hay que decidirla)

- [ ] **Shopify Plus vs. Basic.** El portal de reórdenes mayoristas con catálogos/precios por cliente (Meta 4.4 del plan ejecutivo) requiere Shopify Plus; hoy la tienda está en Basic. Se puede resolver más adelante, cuando se necesite ese portal — no es un bloqueador para el estado actual del sitio (catálogo vivo + landing de captación).

## Chequeo general sugerido (no documentado como pendiente en ningún doc fuente — verificar antes de dar por cerrado el bloque)

- [ ] **Analytics/tracking** (Google Analytics o Meta Pixel). No hay registro de que esté instalado. El plan de validación mide "costo por degustación agendada < $25 USD" (Meta 2.5), lo cual necesita tracking real para poder medirse.
- [ ] **Páginas legales** (política de privacidad, términos). Shopify las genera por defecto en el footer (`footer-utilities`, ver build-log 31 jul), pero no hay registro de que alguien haya revisado que el contenido sea real de Xocolata y no el placeholder genérico de Shopify.

## Ya resuelto (referencia — no repetir)

Todo lo demás del sitio ya está construido y verificado en vivo: nombre de tienda y tema publicado, logo real integrado (header + favicon), inglés enrutable con selector nativo del tema, home bilingüe completo (hero con video, "Nuestra Historia" a nivel nacional, cómo funciona, Garantía Triple Sello con íconos reales, comparativa vs. competencia rediseñada con íconos, insumos a futuro, FAQ), 4 páginas de producto con ficha nutricional real, footer de marca, correo de contacto unificado en todos los puntos, countdown en vivo a la feria de Miami, carrusel de la colección enlazado a cada producto, peso real de la Empanada corregido (80 g). Detalle completo día a día en [build-log.md](build-log.md).

Ver también [decisiones abiertas](../decisiones-abiertas.md), [roadmap.md](../roadmap.md) y [rol de Shopify](rol-de-shopify.md).
