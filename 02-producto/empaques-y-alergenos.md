# Empaques y comunicación de alérgenos (gluten)

> Fuente: nota de reunión del 18 de julio de 2026.

## El problema detectado

Al revisar el diseño de las bolsas surgió una alerta: las piezas gráficas muestran **espigas de trigo**, y para el consumidor norteamericano esa imagen **asocia automáticamente el producto con gluten** — así el producto no lleve harina de trigo. La maquiladora (Daka) ya advirtió sobre esto explícitamente: "el norteamericano asocia trigo con gluten automáticamente."

- De los 4 productos del [portafolio](portafolio.md) (Buñuelo Relleno, Pandebono en Rosca, Almojábana Especial, Empanada de Cambray), **solo la Empanada de Cambray lleva harina** (de trigo, por la masa de la empanada).
- Los otros tres son naturalmente a base de almidón de yuca/maíz y queso — candidatos a comunicarse como **libres de gluten**.
- La tabla nutricional que entrega la maquiladora solo certifica que lácteos y huevos están pasteurizados (requisito FDA) — **no dice nada sobre gluten**, ni en un sentido ni en otro.

> **⚠️ Corrección importante (31 jul, con datos reales del empaque final):** el supuesto de arriba ("los otros tres son candidatos gluten-free") **resultó incorrecto para la Almojábana**. El diseño de empaque final recibido de Daka (`Material grafico/branding-generado/XOCOLATA X4 REF.pdf`) lista los ingredientes reales por producto, y la Almojábana Especial **sí contiene harina de trigo**, con el empaque declarando explícitamente "Contiene: Leche y gluten". Es decir: de los 4 productos, **solo Buñuelo Relleno y Pandebono en Rosca** muestran ingredientes sin trigo en este documento — y ambos **siguen sin la certificación formal de Daka** pendiente más abajo. La Empanada de Cambray y la Almojábana Especial quedan descartadas como candidatas gluten-free. Ningún claim "gluten free" está publicado hoy en Shopify (verificado — no hay tag de gluten en ningún producto), así que no hay nada que corregir en el sitio en vivo, pero **cualquier futura comunicación de "libre de gluten" debe basarse en esta lista de 2, no en la de 3 original.**

## Decisión a validar

1. **Rediseñar el empaque**: mantener la estética pero quitar las espigas de trigo del diseño gráfico. *(Resuelto en el diseño final — ver nota de abajo.)*
2. Agregar comunicación explícita **"Gluten Free"** en los productos donde aplique (**Pandebono y Buñuelo únicamente**, no Almojábana — ver corrección arriba).
3. Evaluar si conviene posicionar toda la asociación de marca (no solo el empaque individual) alrededor de "gluten free" como diferenciador — a validar según cuántos productos puedan certificarse.

## Siguiente paso (pendiente, urgente)

- **Preguntar directamente al maquilador (Daka)** qué productos pueden certificarse formalmente como libres de gluten — Xocolata opera bajo los permisos de él, así que la certificación depende de su proceso, no solo del diseño.
- El diseño de bolsas y de la página lo maneja una **diseñadora externa** — hay que enviarle el ajuste. Ver [personas y contactos](../personas-y-contactos.md).
- ⚠️ **Van atrasados con las bolsas.** El despacho del contenedor sale el **15 de agosto de 2026** — ver fecha actualizada en [costos, precios y logística](../03-operacion/costos-precios-logistica.md). Este ajuste de diseño debe cerrarse cuanto antes para no poner en riesgo esa fecha.

## Diseño final de empaque recibido (31 jul) — estado real

Daka entregó el diseño de empaque final y listo para imprimir para los 4 productos: `Material grafico/branding-generado/XOCOLATA X4 REF.pdf` (16.75 × 25 cm, frente con ventana transparente + reverso con tabla nutricional, ingredientes, instrucciones, historia de marca, QR y código de barras). Hallazgos al revisarlo:

- **Las espigas de trigo ya no están** — el diseño final usa un motivo de ramas doradas (laurel) a los lados del logo, no el motivo de trigo que generó la alerta original. Ese punto queda resuelto.
- **Corrección de gluten aplicada solo parcialmente:** el problema de fondo (asociación visual con trigo) se resolvió, pero el hallazgo de que la Almojábana sí contiene trigo (ver arriba) sigue vigente — sin relación con el diseño gráfico, es la fórmula real del producto.
- **Inconsistencia en la regla de "Pasteurizado" (ver abajo):** el ingrediente del Pandebono en Rosca lista "mantequilla" y "leche" **sin** el calificativo "pasteurizada/o", a diferencia de los otros 3 productos que sí lo aplican consistentemente en sus quesos. Vale la pena pedirle a Daka/la diseñadora que lo ajuste antes de imprimir, para mantener la consistencia de la regla definida el 21 jul (ver abajo).

## Corrección final de gluten (31 jul, con el panel nutricional real leído completo)

Al construir las páginas de detalle de producto se leyó línea por línea el panel nutricional real de los 4 productos (`XOCOLATA X4 REF.pdf`), no solo la ficha resumen usada en las correcciones anteriores. Resultado — **la lista de candidatos gluten-free cambia otra vez, y esta vez en sentido contrario**:

| Producto | Harina | Declaración CONTIENE (empaque real) |
|---|---|---|
| Empanada de Cambray | Harina de **maíz** (no trigo) | Leche, derivados lácteos |
| Pandebono en Rosca | Harina de maíz | Leche, derivados lácteos |
| Buñuelo Relleno | Sin harina de trigo | Leche, derivados lácteos y huevo |
| Almojábana Especial | Harina de **trigo** | **Leche y gluten** |

Es decir: de los 4 productos, **solo la Almojábana Especial contiene gluten** — la Empanada de Cambray, que se había asumido con trigo desde el primer documento de este archivo, en realidad no lo lleva según el empaque final impreso. Esto invierte la suposición original ("solo la Empanada lleva trigo") y también la corrección del 31 jul anterior (que asumía Empanada + Almojábana como no-candidatas). Esta tabla, basada en el panel nutricional real, es la fuente de verdad más reciente.

Ningún producto muestra un sello "Gluten Free" en el sitio — se optó por mostrar los ingredientes tal como están impresos en el empaque, sin hacer el claim, ya que la certificación formal con Daka sigue pendiente (ver siguiente paso, abajo). Aplicado en las páginas de detalle de producto — ver [build-log](../08-shopify/build-log.md).

## Regla de etiquetado: huevo y lácteos siempre como "pasteurizado"

**Convención obligatoria (definida 21 jul):** en cualquier lista de ingredientes, ficha técnica o empaque, todo ingrediente a base de huevo o lácteo debe nombrarse con el calificativo **"Pasteurizado"** — nunca el ingrediente solo.

- ✅ "Huevo Pasteurizado" · ✅ "Mantequilla Pasteurizada" · ✅ "Queso Pasteurizado"
- ❌ "Huevo" · ❌ "Mantequilla" · ❌ "Queso" (sin el calificativo)

**Por qué:** es el mismo requisito FDA que ya certifica la maquiladora en la tabla nutricional (ver arriba) — lácteos y huevos deben acreditarse como pasteurizados. Usar el calificativo en toda pieza de cara al cliente (empaque, ficha técnica, web) mantiene la comunicación consistente con lo que ya está certificado, y refuerza el argumento de calidad/trazabilidad ante el comprador B2B.

**Dónde aplica:** ninguna lista de ingredientes está redactada todavía en este repo (la ficha técnica es parte de la Meta 1.2 pendiente — ver [decisiones abiertas](../decisiones-abiertas.md)); esta regla queda anotada para aplicarse **desde el primer borrador** de esa ficha, del empaque, y de cualquier producto que se cargue a Shopify con ingredientes listados.

Ver también [portafolio de producto](portafolio.md), [modelo y permisos](../03-operacion/modelo-y-permisos.md) y [decisiones abiertas](../decisiones-abiertas.md).
