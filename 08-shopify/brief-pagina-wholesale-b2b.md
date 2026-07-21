# Brief: página Shopify wholesale B2B (bilingüe ES/EN)

> Define qué vamos a construir en Shopify y con qué narrativa, antes de tocar el tema. Complementa [rol de Shopify](rol-de-shopify.md) (el porqué estratégico) con el cómo concreto. Copy con enfoque de **alta conexión emocional**, dirigido a los 4 clusters de comprador B2B en EE. UU.

## Objetivo de la página

Una página bilingüe (español/inglés) que convierta a un dueño de negocio latino o distribuidor en EE. UU. en un **lead de WhatsApp** — no en un checkout con tarjeta. El objetivo no es vender online hoy; es que cuando un comprador busque a Xocolata en Google (antes de responder un correo, o después de ver un ad/degustación), encuentre una vitrina seria, emotiva y clara que lo empuje a escribir "quiero trabajar con ustedes".

Foco: los **4 productos de Fase 1** — Empanada de Cambray, Pandebono en Rosca, Buñuelo Relleno, Almojábana Especial (ver [portafolio](../02-producto/portafolio.md)).

---

## Diagnóstico del estado actual de la tienda (lo que encontré)

Revisé la tienda conectada (`gjkkyq-ac.myshopify.com`) el 21 de julio de 2026. Está prácticamente en ceros y con configuración por defecto de Colombia:

| Área | Estado actual | Qué implica |
|---|---|---|
| Nombre de la tienda | "Mi tienda" (por defecto) | Hay que ponerlo como **Xocolata Food Premium** |
| Idioma | Solo español (`es`), único publicado | Falta agregar **inglés** — es la mitad del pedido |
| Mercado | Solo Colombia, moneda COP | Falta mercado/visualización para **EE. UU. (USD)** |
| Productos | 1 de 4 (**Pandebono**, activo pero con **0 inventario**, precio 49.700 COP retail) | Faltan 3 productos + revisar precio/moneda del que hay |
| Colecciones | Solo "Página de inicio" (frontpage) por defecto | Falta una colección **"Colección Mayorista / Wholesale"** |
| Páginas | Solo "Contacto" | Falta la landing B2B, "cómo funciona", "quiénes somos" |
| Plan | Basic | ⚠️ Ver limitación de B2B nativo abajo |

**Traducción:** no estamos "editando" una tienda existente, estamos **construyéndola casi desde cero**. Eso es bueno — no hay que deshacer nada.

---

## Realidad técnica y legal (leer antes de decidir la arquitectura)

Tres restricciones que definen qué se puede y qué no se puede hacer **hoy**:

### 1. La LLC en EE. UU. todavía está en trámite
Sin la LLC constituida no se puede procesar pagos con tarjeta de EE. UU. ni operar legalmente como empresa estadounidense. **Conclusión:** la página **no debe tener checkout activo hacia clientes de EE. UU. todavía.** No prometemos "compra ahora"; invitamos a "hablemos". Esto además coincide perfectamente con la estrategia: el comprador B2B **cierra por WhatsApp, no por carrito** (ver [rol de Shopify](rol-de-shopify.md) y [estrategia de contenido y ads](../05-contenido-y-marketing/estrategia-contenido-ads.md)).

### 2. El B2B nativo de Shopify requiere plan Plus
Las funciones "de verdad" de wholesale (perfiles de empresa, catálogos por cliente, listas de precio, net terms) son **exclusivas de Shopify Plus**. En plan **Basic** no existen. Las alternativas realistas en Basic:
- **"Solicitar cotización" / precios ocultos** → botón que lleva a WhatsApp o a un formulario (recomendado, y es lo que la estrategia ya pide).
- Apps de wholesale de terceros (costo mensual, se evalúan más adelante si hace falta).
- Área con contraseña ("wholesale login") para aliados ya aprobados — posible en Basic de forma sencilla.

**Conclusión:** no dependemos de funciones Plus. Construimos un **catálogo + landing de captación** que empuja a WhatsApp. La automatización de re-orden mayorista (Meta 4.4) se resuelve después, cuando haya aliados cerrados y se evalúe si vale la pena Plus o una app.

### 3. Los precios/márgenes aún no están cerrados
La ficha de rentabilidad sigue pendiente (ver [decisiones abiertas](../decisiones-abiertas.md)). **Conclusión:** no publicamos precios en la página. Los precios van en la conversación de WhatsApp / cotización. Esto también es lo correcto en B2B: el precio se da al cliente calificado, no en la vitrina pública.

> **Recomendación de fondo:** la página, en esta fase, es una **landing de captación bilingüe con catálogo de vitrina** que lleva a WhatsApp — **no una tienda transaccional**. Si el equipo quiere checkout real más adelante, es una Fase B posterior a la LLC. Si no están de acuerdo con esto, es la primera decisión a discutir.

---

## Qué organizar y subir (checklist)

### Configuración de la tienda
- [ ] Cambiar nombre de la tienda a **Xocolata Food Premium**.
- [ ] Subir logo (óvalo dorado) y favicon; definir colores de marca (vinotinto/dorado) en el tema.
- [ ] Agregar el idioma **inglés** (app gratuita *Translate & Adapt* de Shopify) y traducir todo el contenido.
- [ ] Decidir moneda/mercado de visualización: mostrar **USD** para el visitante de EE. UU. (se puede activar un mercado "Estados Unidos" para display de moneda **sin** activar checkout con tarjeta).
- [ ] Configurar el selector de idioma ES/EN visible en el encabezado.

### Productos (los 4 de Fase 1)
Para cada uno: nombre, descripción emotiva bilingüe, fotos (corte transversal como firma), presentaciones/formatos (retail y food service), tags, y **precio oculto o "cotizar"** en vez de precio público.
- [ ] Empanada de Cambray (producto ancla)
- [ ] Buñuelo Relleno (arequipe / guayaba)
- [ ] Almojábana Especial
- [ ] Pandebono en Rosca — **revisar el existente**: hoy está como "Pandebonos", 0 inventario, precio en COP retail y con tag "sin gluten" (⚠️ la certificación gluten free aún no está confirmada — ver [empaques y alérgenos](../02-producto/empaques-y-alergenos.md); quitar ese tag hasta validarlo).

### Colecciones y páginas
- [ ] Colección **"Colección Mayorista / Wholesale Collection"** con los 4 productos.
- [ ] Página principal (landing B2B) — la narrativa completa de abajo.
- [ ] Página "Cómo funciona / How it works" (bake-off 8 min, cadena de frío, Triple Sello).
- [ ] Página "Quiénes somos / Our story" (la historia de marca, emotiva).
- [ ] Página/bloque "Sé nuestro aliado / Become a partner" con el formulario o CTA a WhatsApp.
- [ ] Revisar/rehacer la página "Contacto" con datos reales (⚠️ el WhatsApp comercial aún no está confirmado — ver [personas y contactos](../personas-y-contactos.md); pedirlo antes de publicar).

### Assets que hacen falta (pedir al equipo o generar)
- [ ] Fotos profesionales de los 4 productos, incluyendo corte transversal.
- [ ] Foto/video del bake-off (sale del [b-roll de la grabación del 23 jul](../05-contenido-y-marketing/guiones-grabacion-23-jul.md)).
- [ ] Clips de reacciones reales de extranjeros (prueba social para el cluster D — misma grabación).
- [ ] Número de WhatsApp comercial confirmado + email + dominio final.

---

## Arquitectura de la página (secciones, en orden)

El orden **es** el argumento de venta — va de la emoción del cliente final a la oportunidad de negocio:

| # | Sección | Qué hace |
|---|---|---|
| 1 | **Hero** | Golpe emocional: "el sabor de casa, listo para tu vitrina" + 2 CTA (WhatsApp / ver catálogo) |
| 2 | **El sabor que tus clientes extrañan** | Conecta con la nostalgia del consumidor latino en EE. UU. — el negocio compra acceso a esa emoción |
| 3 | **La colección (4 productos)** | Vitrina de los 4, con foto de corte transversal y descripción emotiva; precio → "cotizar" |
| 4 | **Cómo funciona (bake-off)** | 8 minutos, sin panadero, sabe a recién horneado aunque es congelado |
| 5 | **Cero riesgo: Triple Sello** | La garantía como mensaje de confianza (ver [identidad](../01-marca/identidad-y-posicionamiento.md)) |
| 6 | **Por qué ser aliado de Xocolata** | Diferenciación, exclusividad por territorio, ser el primero |
| 7 | **Quiénes somos** | Historia de marca: tradición colombiana con estándar de exportación |
| 8 | **Prueba social** | Clips de reacciones + (a futuro) casos de aliados "Primeros 10" |
| 9 | **CTA final / Sé nuestro aliado** | Formulario corto o botón directo a WhatsApp, bilingüe |

---

## La narrativa: por qué un cluster debería trabajar con Xocolata

El eje emocional no es "compra buñuelos congelados". Es **doble**:

1. **La emoción del cliente final que el negocio compra:** la nostalgia. El latino en EE. UU. extraña el sabor de casa; los padres migrantes quieren que sus hijos —nacidos allá— conozcan de dónde vienen. Xocolata le da al negocio la capacidad de **entregar ese pedazo de hogar**, recién horneado.
2. **La emoción del propio dueño de negocio:** el orgullo de ser quien trae eso, ser el **primero** en su zona, tener el producto del que todos hablan — y hacerlo **sin riesgo y sin complicar su cocina**.

El arco: *Tus clientes extrañan casa → hoy no puedes dárselo bien (no tienes panadero, los congelados saben a fábrica) → Xocolata lo resuelve (8 min, sabe a recién hecho) → sin riesgo (Triple Sello) → y llegas primero (territorio) → hablemos.*

### Copy de muestra (dirección de tono — la versión completa por sección es el siguiente paso)

**Hero**
- **ES:** *(antetítulo)* Panadería colombiana premium · Congelada · Lista en 8 minutos
  **El sabor de casa, listo para tu vitrina.**
  Tus clientes crecieron con este sabor. Ahora puedes ofrecérselo recién horneado —sin panadero y sin complicaciones— directo desde Colombia a tu negocio en Estados Unidos.
  `[Hablemos por WhatsApp]` `[Ver el catálogo mayorista]`
- **EN:** *(eyebrow)* Premium Colombian bakery · Frozen · Ready in 8 minutes
  **The taste of home, ready for your counter.**
  Your customers grew up with this flavor. Now you can serve it fresh-baked —no baker, no hassle— straight from Colombia to your business in the United States.
  `[Let's talk on WhatsApp]` `[See the wholesale catalog]`

**El sabor que tus clientes extrañan**
- **ES:** Para muchos de tus clientes, un pandebono no es solo pan: es la casa de la abuela, es el desayuno de domingo, es Colombia en un bocado. Ese recuerdo hoy no lo encuentran en ningún estante. Tú puedes ser quien se los devuelva.
- **EN:** For many of your customers, a pandebono isn't just bread — it's grandma's kitchen, it's Sunday breakfast, it's Colombia in a single bite. Right now, that memory isn't on any shelf near them. You can be the one who brings it back.

**Cero riesgo (Triple Sello)**
- **ES:** Sabemos que apostarle a una marca nueva da miedo. Por eso el riesgo lo asumimos nosotros: si falla la cadena de frío, reponemos. Si tu primera orden no rota en 45 días, llevamos degustaciones y contenido a tu punto de venta, sin costo. Tú solo decides con el producto en la mano.
- **EN:** We know betting on a new brand feels risky. So we take the risk: if the cold chain fails, we replace it. If your first order doesn't sell in 45 days, we bring tastings and content to your location — at no cost. You just decide with the product in your hands.

**CTA final**
- **ES:** Miami elige territorio primero. Escríbenos hoy y agenda una degustación antes de la feria.
  `[Hablemos por WhatsApp]`
- **EN:** Miami picks territory first. Message us today and book a tasting before the show.
  `[Let's talk on WhatsApp]`

> El tono sigue la voz de marca definida en [identidad y posicionamiento](../01-marca/identidad-y-posicionamiento.md): socio comercial con orgullo de origen, bilingüe según la cuenta, **sin spanglish forzado**. Emotivo pero nunca cursi; cada sección responde una pregunta del comprador (emoción, operación, riesgo, oportunidad).

---

## Enfoque bilingüe (cómo se implementa)

- Español = idioma primario (ya lo es). Inglés = segundo idioma vía *Translate & Adapt* (gratis, oficial de Shopify).
- **No es traducción literal.** El inglés se **adapta** al comprador de EE. UU. (ej. el hero en inglés apela más a "the taste of home" que a una traducción palabra por palabra). Cada idioma tiene su propia versión trabajada.
- Selector ES/EN visible en el header. La URL cambia por idioma (`/en/...`) — bueno para SEO.
- El contenido que la audiencia real (EE. UU.) más va a ver debe estar impecable en **inglés**; el español sirve para el comprador latino bilingüe y para el mercado colombiano/mismo equipo.

---

## Fases

**Fase A — ahora (pre-LLC):** catálogo + landing bilingüe de captación → WhatsApp. Sin checkout. Precios ocultos/"cotizar". Es lo que construimos con este brief.

**Fase B — después (post-LLC + producto en EE. UU.):** evaluar activar mercado EE. UU. con USD y checkout real; portal de re-orden mayorista para aliados aprobados (Meta 4.4) — decidir entonces entre área con contraseña, app de wholesale, o upgrade a Plus.

---

## Siguiente paso

Con este brief aprobado, el siguiente entregable es el **copy completo bilingüe sección por sección** (los 9 bloques, ES + EN, listos para pegar en Shopify) en un archivo aparte — mismo patrón que usamos con el brochure (brief → luego el detalle). Después de eso, la construcción efectiva en el tema de Shopify (subir productos, crear páginas, configurar idioma/mercado).

Ver también [rol de Shopify](rol-de-shopify.md), [identidad y posicionamiento](../01-marca/identidad-y-posicionamiento.md), [portafolio](../02-producto/portafolio.md) y [guía comercial y plantillas](../04-estrategia-b2b/guia-comercial-y-plantillas.md).
