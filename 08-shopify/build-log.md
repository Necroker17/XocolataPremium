# Build log — construcción de la página wholesale

> Registro de lo efectivamente construido en la tienda Shopify `gjkkyq-ac.myshopify.com`, siguiendo el [brief](brief-pagina-wholesale-b2b.md) y el [copy](copy-pagina-wholesale.md). Fecha de construcción: 21 de julio de 2026.

## Lo que quedó construido

| Elemento | Estado | Detalle |
|---|---|---|
| Idioma inglés | ✅ Hecho | Locale `en` habilitado y publicado (vía API). Ahora la tienda soporta ES (primario) + EN. |
| Empanada de Cambray | ✅ Creado (borrador) | Descripción emotiva ES. `gid://shopify/Product/10487437721888` |
| Buñuelo Relleno | ✅ Creado (borrador) | `gid://shopify/Product/10487437787424` |
| Almojábana Especial | ✅ Creado (borrador) | `gid://shopify/Product/10487437885728` |
| Pandebono en Rosca | ✅ Corregido (borrador) | Renombrado (era "Pandebonos…"), descripción nueva, **tag "sin gluten" eliminado**. `gid://shopify/Product/10473549398304` |
| Colección Mayorista | ✅ Creada | Los 4 productos, orden manual (Empanada primero). Handle `coleccion-mayorista`. |
| Landing bilingüe | ✅ Publicada | Página Shopify handle **`mayorista`** → `…/pages/mayorista`. Las 9 secciones del copy, ES/EN con toggle. |
| Preview navegable | ✅ | Artifact: la landing completa con el toggle ES/EN funcionando (link compartido aparte). Fuente en [landing-wholesale.html](landing-wholesale.html). |

### Por qué los productos están en **borrador**
Decisión del [brief](brief-pagina-wholesale-b2b.md): mientras la LLC esté en trámite y la ficha de rentabilidad sin cerrar, no exponemos checkout ni precios públicos. La cara pública es la landing (que lleva a WhatsApp/email). Los productos quedan como catálogo interno, listos para activarse en la Fase B. Por eso también sus precios están en `0.00` (placeholder — "precio bajo cotización").

## Pendiente (no se pudo hacer por API o requiere decisión)

- [ ] **Nombre de la tienda** sigue como "Mi tienda". No es editable por API → cambiarlo manualmente en Shopify Admin → *Configuración › Datos de la tienda* a **Xocolata Food Premium**.
- [ ] **Número de WhatsApp:** los CTA de la landing hoy apuntan a `mailto:comercial@xocolatafoodpremium.com`. Cuando se confirme el número, reemplazar por `https://wa.me/{{WHATSAPP}}` (hay un comentario `TODO` en el HTML marcando los dos puntos). Ver [decisiones abiertas](../decisiones-abiertas.md).
- [ ] **Fotos de producto:** los productos y las tarjetas de la landing no tienen foto real todavía (placeholders con el nombre). Falta la sesión de fotos / usar el b-roll de la [grabación del 23 jul](../05-contenido-y-marketing/guiones-grabacion-23-jul.md).
- [ ] **Traducción EN a nivel de producto:** las descripciones de producto están en español (la landing sí es bilingüe). Registrar traducciones EN de los 4 productos vía *Translate & Adapt* cuando se activen (Fase B).
- [ ] **Verificar render en el tema:** la página `/pages/mayorista` usa `<style>` propio scopeado en `.xoc` y un toggle con `:has()`. Conviene abrirla en el navegador para confirmar que el tema no recorta el `<style>`; si lo recorta, se monta como sección de tema (Fase B) o se deja el Artifact como referencia de diseño.
- [ ] **Moneda/mercado USD:** hoy la tienda muestra COP. Para el visitante de EE. UU. conviene activar visualización en USD (mercado "Estados Unidos") — sin activar checkout con tarjeta mientras no exista la LLC.
- [ ] **Selector de idioma del tema:** la landing trae su propio toggle interno, pero el resto de la tienda necesita el selector ES/EN del tema activado en la configuración del tema.

## Cómo actualizar la landing

La fuente de diseño es [landing-wholesale.html](landing-wholesale.html) (versionada en git). Para cambiar la página en Shopify: editar ese archivo y volver a subir el `body` a la página `mayorista` (mutación `pageUpdate`), o pegarlo en el editor de la página en Shopify Admin. El Artifact se actualiza volviendo a publicar el mismo archivo.

Ver también [brief](brief-pagina-wholesale-b2b.md), [copy](copy-pagina-wholesale.md) y [rol de Shopify](rol-de-shopify.md).
