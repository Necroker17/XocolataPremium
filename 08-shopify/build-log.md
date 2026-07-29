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
- [x] **Verificar render en el tema:** confirmado en navegador — `/pages/mayorista` renderiza bien, el `<style>` no se recorta, sin errores de consola.
- [ ] **Moneda/mercado USD:** hoy la tienda muestra COP. Para el visitante de EE. UU. conviene activar visualización en USD (mercado "Estados Unidos") — sin activar checkout con tarjeta mientras no exista la LLC.
- [ ] **Selector de idioma del tema:** la landing trae su propio toggle interno, pero el resto de la tienda necesita el selector ES/EN del tema activado en la configuración del tema.

## Cómo actualizar la landing

La fuente de diseño es [landing-wholesale.html](landing-wholesale.html) (versionada en git). Para cambiar la página en Shopify: editar ese archivo y volver a subir el `body` a la página `mayorista` (mutación `pageUpdate`), o pegarlo en el editor de la página en Shopify Admin. El Artifact se actualiza volviendo a publicar el mismo archivo.

## Tema a medida (21 jul) — "realmente llamativo"

El tema activo es **Horizon** (el más nuevo de Shopify). En vez de dejar el home de demostración, se construyó una **portada de marca a medida por código** (Shopify CLI), sobre una **copia no publicada** para no tocar el tema en vivo.

**Qué se hizo:**
- **Identidad global del tema** (`config/settings_data.json`): paleta vinotinto/dorado/crema (background `#F7F1E3`, foreground `#4A0E1E`, acento `#C9A24B`) y fuentes Playfair Display (títulos) + Assistant (cuerpo).
- **Sección propia** `sections/xoc-home.liquid`: hero a pantalla completa con foto real, narrativa emocional, colección de 4 productos con foto, "cómo funciona", Triple Sello, "por qué ser aliado" y CTA final. Bilingüe vía `request.locale.iso_code` (sigue el selector nativo de Shopify). Fuentes de marca cargadas por Google Fonts. CTA editable desde el editor de tema (setting `cta_url`).
- **Home** (`templates/index.json`): apunta solo a la sección `xoc-home`.
- **Imágenes provisionales**: 5 fotos recortadas del deck (hero del grupo sobre mármol + los 4 productos en corte), optimizadas a JPG, en `assets/` del tema. Copia para el equipo en `Material grafico/productos-interinos-deck/`.

**⚠️ Tema "Xocolata Premium (desarrollo)" (id 190111580448) — ahora es el tema EN VIVO de la tienda.** Se publicó el 21 de julio (el equipo lo hizo directamente desde el Admin). El tema original **Horizon queda como respaldo, sin publicar** (id 189990895904) — si algo sale mal, se puede volver a publicar ese para restaurar el estado anterior.
- Sitio en vivo: `https://gjkkyq-ac.myshopify.com`
- Editor: `https://gjkkyq-ac.myshopify.com/admin/themes/190111580448/editor`
- Verificado en consola: sin errores de Liquid ni de JavaScript.

### Iteración de diseño (21 jul, tras revisar el tema "Zeal" de la Theme Store)
El usuario revisó un tema de pago ($270 USD, orientado a suplementos/wellness) buscando más energía visual. Se rescataron **el impacto y las funciones**, no la piel naranja/deportiva (que no encaja con el posicionamiento premium colombiano). Se agregó a `xoc-home.liquid`:
- **Ticker animado** (franja dorada, texto vinotinto en movimiento) con las frases clave de marca — pausa automática si el usuario tiene `prefers-reduced-motion`.
- **Countdown real a la feria de Miami** (14 sep 2026, con JavaScript vanilla, sin dependencias) — urgencia genuina, no una oferta falsa. Con fallback `<noscript>` si el visitante tiene JS desactivado.
- **Badges de mayorista** ("Mín. 1 caja · Precio por volumen") en cada tarjeta de producto — inspirado en el patrón de precios por cantidad de Zeal, adaptado a que aún no publicamos precios.

**El código a medida está versionado** en [theme-custom/](theme-custom/) (`xoc-home.liquid`, `index.json`). El tema completo vive local en `../Shopify/xocolata-theme/` y en Shopify como tema de desarrollo.

### Correcciones y contenido de caja (21 jul, misma sesión)

- **Relleno del Buñuelo corregido en todo el sitio:** "arequipe o queso" (no guayaba) — actualizado en el tema en vivo (`xoc-home.liquid`), la descripción del producto en Shopify, y la página `/pages/mayorista`.
- **Contenido de la caja agregado a los 4 productos**, en la home, en `/pages/mayorista` y en la descripción de cada producto en Shopify (presentación **retail**, la food service difiere y se ofrece al cotizar):
  - Empanada de Cambray: 4 paquetes de 20 (80 empanadas, 60 g c/u).
  - Buñuelo Relleno: 20 bolsas de 6 (120 buñuelos).
  - Almojábana Especial: 20 bolsas de 10 (200 almojábanas).
  - Pandebono en Rosca: 20 bolsas de 6 (120 pandebonos).
  - Fuente de los datos: [costos, precios y logística](../03-operacion/costos-precios-logistica.md).
- La página `/pages/mayorista` (versión previa al home a medida) seguía con contenido desactualizado — se corrigió también para que no quede una versión vieja del sitio dando vueltas.

### Pendiente del tema
- [ ] **Publicarlo** (tu decisión) — desde Shopify Admin › Temas › "Xocolata Premium (desarrollo)" › Publicar.
- [ ] **Nombre de la tienda** "Mi tienda" → "Xocolata Food Premium" (el encabezado del tema muestra ese nombre hasta que se cambie / se suba un logo).
- [ ] **Logo** en el encabezado: subir PNG transparente en el editor de tema.
- [ ] **Inglés visible para visitantes:** el contenido EN ya está en el tema, pero la ruta `/en` necesita que un **mercado** ofrezca inglés (hoy solo existe el mercado Colombia en ES). Al activar el mercado de EE. UU. con inglés (y USD), el selector de idioma empieza a funcionar. Pareado con la decisión de USD.
- [ ] **Fotos reales** reemplazan las provisionales del deck cuando estén (b-roll del 23 jul).
- [ ] **WhatsApp:** el botón usa `mailto` hasta confirmar el número; se cambia en el setting `cta_url` de la sección.

### Animaciones y UX cinematográfico (22 jul) — inspirado en Zeal y Ryze Superfoods

Se vendorizó **GSAP + ScrollTrigger** localmente (`assets/gsap.min.js`, `assets/gsap-scrolltrigger.min.js` — sin CDN externo) y se creó `assets/xoc-animations.js` como motor de animación central:
- Sistema de reveals por atributo (`data-anim="fade-up"`, `data-anim="stagger"`) reutilizable en cualquier sección nueva.
- Respeta `prefers-reduced-motion` vía `gsap.matchMedia()`.
- Red de seguridad: si algo falla, ningún elemento queda oculto permanentemente (timeout de rescate + `ScrollTrigger.refresh()` tras cargar fuentes web, para evitar el bug de triggers desincronizados por fuentes que cargan tarde).

**Sección "La colección" reconstruida** como carrusel horizontal con scroll-snap nativo + barra de progreso segmentada sincronizada al scroll (patrón tomado de la sección "Core Vitality Collection" del tema Zeal) — cada una de las 4 tarjetas de producto escala/resalta al estar en foco, y los segmentos de la barra se llenan según cuánto se ha recorrido el carrusel.

Se usó `shopify theme dev --theme 190111580448` para iterar en vivo (el tema live-sincroniza cambios en tiempo real, mismo patrón que ya se usaba con `--allow-live` en `theme push`).

**Bugs encontrados y corregidos en esta sesión:**
- El carrusel completo estaba envuelto en un `data-anim="fade-up"` — si el trigger de scroll se desincronizaba (ej. por carga tardía de fuentes), toda la sección de productos podía quedar invisible. Se quitó el fade del contenedor del carrusel; el contenido de producto ya no depende de un scroll-trigger para aparecer.
- **Footer sin personalizar:** el bloque "Join our email list" seguía en inglés, genérico, con links a redes sociales placeholder (`facebook.com/`, `instagram.com/` sin handle real). Se reemplazó por un bloque de marca en español ("Xocolata Food Premium" + contacto) y se quitaron el formulario de newsletter y los links sociales falsos (decisión: no publicitar redes que no existen, mismo criterio que con el número de WhatsApp — ver [decisiones abiertas](../decisiones-abiertas.md)).
- **Barra de anuncio en inglés:** "Welcome to our store" (default de Horizon) → reemplazado por el mensaje real de campaña ("Agenda tu degustación antes de la feria de Miami · 14–16 sep 2026").

Ver la auditoría completa de patrones de Ryze Superfoods y el plan de adaptación en [propuesta de arquitectura inspirada en Ryze](propuesta-arquitectura-inspirada-ryze.md).

### Primera tanda de "quick wins" de la propuesta Ryze (22 jul) — completa
Los 5 quick wins de la [propuesta de arquitectura](propuesta-arquitectura-inspirada-ryze.md) ya están construidos y probados en el navegador:
- [x] **Ticker sticky** — queda fijo justo debajo del header al hacer scroll (altura del header medida en tiempo real por JS, vía `--xh-header-h`, para no depender de un valor fijo que se desactualice).
- [x] **Botón flotante "Hablemos"** — aparece con `IntersectionObserver` en cuanto el visitante sale del hero, sigue el scroll el resto de la página.
- [x] **Fila de atributos con ícono** en "Cómo funciona" — -18°C · 8 MIN HORNO · HUEVO PASTEURIZADO · PRODUCTO COLOMBIANO, íconos de línea dorada.
- [x] **Badge de Garantía Triple Sello** repetible — versión compacta (ícono de escudo + una línea) agregada junto al CTA final.
- [x] **Sección FAQ** con acordeón nativo (`<details>/<summary>`, sin JS extra) — 6 preguntas reales de comprador B2B (mínimos, cobertura, personal, garantía, precio, cumplimiento FDA). Contenido grounded en lo que ya existe en otros documentos — sin inventar datos como plazos de vencimiento o certificaciones no confirmadas (HACCP sigue pendiente, no se reclama como lista).

### Bug real confirmado y corregido (22 jul, tarde): contenido invisible según tamaño de ventana
El usuario reportó que partes de la página (la fila de atributos, el FAQ) se veían en blanco y solo aparecían **después de maximizar la ventana**. Se reprodujo: el sistema de reveals usaba `ScrollTrigger` de GSAP, que calcula de antemano la posición en píxeles donde debe dispararse cada animación. Esa posición se desincroniza del layout real en ciertos tamaños de ventana (no solo maximizada) y el contenido se queda en `opacity:0` permanentemente — hasta que un evento de resize fuerza a GSAP a recalcular.

**Corregido:** se reemplazó `ScrollTrigger` por `IntersectionObserver` nativo del navegador para decidir cuándo animar cada elemento. `IntersectionObserver` no depende de una foto fija de posiciones — el navegador lo evalúa contra el layout real de forma continua, así que no se puede desincronizar de la misma manera. Se probó explícitamente en ventanas de 900×600 y 700×500 (sin maximizar ni redimensionar) y el contenido aparece correctamente desde la primera carga.

### Segundo bug real confirmado y corregido (22 jul): el carrusel no se podía mover con mouse normal
El usuario reportó "el horizontal no está funcionando" — el carrusel de la colección técnicamente sí podía hacer scroll (confirmado por JS), pero **no había ninguna forma de activarlo con un mouse normal**: la scrollbar estaba escondida a propósito (por estética) y solo funcionaba con gestos de trackpad. Corregido con tres mecanismos:
- **Botones de flecha** (prev/next) visibles a los lados del carrusel, con estado disabled/oculto en los extremos.
- **Arrastre con mouse** (mousedown/mousemove) — cursor cambia a "grab"/"grabbing".
- **Rueda del mouse traducida a horizontal** al pasar por encima del carrusel — pero solo mientras haya espacio para moverse en esa dirección, para que nunca "atrape" al visitante sin poder seguir bajando la página.

Nota aparte: las flechas inicialmente se escondían por debajo de 700px de ancho — ese umbral resultó demasiado agresivo (ventanas de escritorio normales, sin maximizar, caen ahí) y las dejaba invisibles justo cuando más se necesitaban. Se quitó ese límite; ahora las flechas se ven en cualquier tamaño de ventana, solo se reducen un poco en pantallas muy angostas (<480px).

### Se retiró la landing duplicada `/pages/mayorista` (22 jul)
El usuario reportó que el carrusel "no funcionaba" — la causa real era que estaba viendo **`/pages/mayorista`**, la landing estática original (`landing-wholesale.html`), completamente separada de `xoc-home.liquid` y sin nada del trabajo de hoy (carrusel, ticker sticky, FAQ, animaciones). Esa página además tenía su propio bug visual (texto del hero superpuesto/fantasma). Confirmado con el usuario: **la página de inicio (`/`, `xoc-home.liquid`) queda como la landing oficial.**

Se retiró `/pages/mayorista`:
- Se creó un URL redirect (`/pages/mayorista` → `/`) vía `urlRedirectCreate`.
- Como Shopify no aplica redirects sobre páginas que todavía existen, se eliminó la página (`pageDelete`, id `gid://shopify/Page/163783278880`) para que el redirect tomara efecto. Verificado: `/pages/mayorista` ahora carga la portada.
- `landing-wholesale.html` (el archivo fuente) queda en el repo como referencia histórica de la primera versión de copy, pero ya no está publicado en la tienda.

**Lección para futuras sesiones:** de ahora en adelante, cualquier verificación en Shopify debe hacerse contra `/` (la portada), no contra `/pages/mayorista` — esa ruta ya no existe como página independiente.

### Tercer bug real confirmado y corregido (22 jul): la navegación se quedaba a mitad de camino
Tras el fix de las flechas, el usuario probó en dos computadores distintos: en uno la navegación se quedaba atascada en Buñuelo (2da tarjeta), en el otro no avanzaba de Empanada. Dos causas combinadas, ambas en la lógica de clic:
1. El botón calculaba a dónde saltar con `carousel.scrollTo({left: paso × índice})` — un valor en píxeles calculado a mano que podía no coincidir exactamente con el punto de "snap" real del navegador, y el navegador lo corregía de vuelta a una tarjeta distinta a la esperada.
2. Ese cálculo dependía de `scrollWidth`/`clientWidth` para saber si ya se había llegado al final — una cuenta que no dio el mismo resultado en los dos computadores probados, dejando el botón "siguiente" deshabilitado antes de tiempo.

**Corregido:** ahora la navegación apunta directo a la tarjeta con `scrollIntoView()` (nunca calcula un píxel a mano) y el estado deshabilitado de las flechas se decide por índice de tarjeta (0 a 3), no por matemática de scroll. También se corrigió que clics rápidos y consecutivos pisaran el índice a mitad de animación. Probado con clics rápidos consecutivos de ida y vuelta (Empanada → Pandebono → Empanada) sin quedarse atascado.

### Cuarto bug real confirmado y corregido (22 jul): saltos erráticos con trackpad
Con las flechas ya funcionando, el usuario reportó que en trackpad el carrusel "se va o se devuelve al primero" de forma errática. Causa: el manejador que redirige la rueda del mouse a movimiento horizontal (agregado para usuarios de mouse normal, sin trackpad) también se activaba con gestos de trackpad — que ya generan su propio movimiento horizontal nativo (`deltaX`). Las dos cosas movían el carrusel al mismo tiempo, compitiendo entre sí y produciendo saltos.

**Corregido:** el redirect de rueda ahora solo se activa cuando el evento no trae ningún componente horizontal (`deltaX === 0`) — la huella de un mouse de rueda simple. Cualquier gesto de trackpad (que siempre trae algo de `deltaX`) se ignora por completo y queda en manos del scroll nativo del navegador, sin interferencia.

### Quinto bug real confirmado y corregido (22 jul): se devolvía a la primera tarjeta al soltar el trackpad
Reportado como "sí funciona pero se devuelve solo" — apenas soltaba el gesto en el trackpad, saltaba de inmediato de vuelta a Empanada de Cambray. Causa: `scroll-snap-type: x mandatory` en el carrusel. Con "mandatory", si un swipe no tiene suficiente impulso/distancia, algunos navegadores (sobre todo con trackpad) interpretan que no hubo intención real de cambiar de tarjeta y fuerzan el regreso a la posición de origen — un comportamiento nativo del navegador, no de nuestro código.

**Corregido:** se cambió a `scroll-snap-type: x proximity`, que solo alinea a la tarjeta más cercana cuando el scroll ya está naturalmente cerca de un punto de snap, sin "pelear" contra el gesto ni forzar un regreso. La navegación por flechas (que usa `scrollIntoView`, no depende del snap-type) no se vio afectada.

### Sexto bug real confirmado y corregido (22 jul): clics rápidos en las flechas terminaban de vuelta en Empanada
El fix del snap-type resolvió el trackpad, pero el usuario reportó que con **clics rápidos** en las flechas sí llegaba hasta Pandebono, pero terminaba devolviéndose a Empanada. Causa: cada clic interrumpía la animación de scroll del clic anterior y la redirigía a una nueva tarjeta; para saber cuándo esa animación "terminaba" se usaba un temporizador fijo de 500ms — con varios clics seguidos redirigiendo la animación una y otra vez, el temporizador del último clic podía disparar *antes* de que el scroll realmente hubiera llegado a su destino final, leyendo una posición intermedia y descuadrando todo.

**Corregido con dos cambios:**
1. Mientras una navegación está en curso, un clic nuevo en las flechas **se ignora** (en vez de redirigir la animación a mitad de camino) — evita que se acumulen animaciones superpuestas.
2. Se reemplazó el temporizador fijo por el evento nativo `scrollend`, que el navegador dispara exactamente cuando el scroll termina de verdad (con respaldo por temporizador solo para navegadores que no lo soporten).

Probado con 4 clics rápidos seguidos en "siguiente": llegó a Pandebono y se quedó ahí sin moverse tras 3 segundos de espera.

### Simplificación radical del carrusel (22 jul, tarde) — se acabaron los parches
Después de varias rondas de arreglos cada vez más elaborados (índice guardado, bandera de "animando", `scrollend`, debounce de clics) que seguían fallando de formas distintas, se rehízo la lógica desde cero de forma mucho más simple: **se eliminó por completo la variable que guardaba "en qué tarjeta estamos".** Ese valor guardado en memoria era la raíz de todos los bugs anteriores — se desincronizaba del scroll real de mil formas distintas según el navegador y la velocidad de los clics.

Ahora cada clic pregunta directo al DOM "¿cuál tarjeta está más cerca del scroll actual?" (comparando posiciones reales, sin memoria) y navega a la vecina desde ahí. No hay bandera de "está animando", no hay temporizador, no hay estado que se pueda desincronizar — porque no hay estado. También se quitó la deshabilitación de las flechas en los extremos (ya no hacía falta): un clic de más en el límite simplemente no mueve nada, sin necesidad de calcular cuándo deshabilitar.

Probado: 3 clics con pausas hasta Pandebono (se queda quieto 3+ segundos sin tocar nada), y un clic extra ya en el límite (no rompe nada, se queda igual).

### Bug raíz encontrado (22 jul, tarde-noche): "ni se mueve" — el carrusel dependía de GSAP sin necesitarlo
Después de la simplificación, el usuario reportó que el carrusel **dejó de moverse por completo**. Causa real, y probablemente la explicación de varias de las rondas anteriores: el archivo tenía `if (typeof gsap === 'undefined') return;` casi al principio, y **todo el código del carrusel y del botón flotante estaba después de esa línea** — aunque ninguno de los dos usa GSAP para nada. Si GSAP fallaba en cargar por cualquier razón (bloqueador de anuncios, firewall corporativo, un fallo de red puntual, una extensión del navegador) todo el resto del script se cortaba silenciosamente, y ningún botón del carrusel quedaba conectado a nada — sin ningún error visible en consola sobre el carrusel mismo.

**Corregido:** se reordenó el archivo. El botón flotante y el carrusel completo (flechas, arrastre, rueda, barra de progreso) ahora corren **siempre**, sin depender de si GSAP cargó. Solo las animaciones decorativas de entrada (fade-up/stagger) — que si son puramente estéticas — quedan detrás del chequeo de GSAP al final del archivo.

**Nota para diagnósticos futuros:** si algo vuelve a "no moverse del todo" (a diferencia de "se mueve pero mal"), revisar primero si algún script externo (GSAP u otro) está fallando en cargar y cortando el resto del archivo silenciosamente.

### Bug real de fondo encontrado y corregido (22 jul, noche): las flechas apenas movían un poco en escritorio
Con la caché ya descartada, el usuario precisó el síntoma: en escritorio, cada clic en una flecha solo corría el carrusel "un poquito" en vez de una tarjeta completa — en celular sí funcionaba bien. Causa raíz: la función que calcula "cuál tarjeta está más cerca" medía la posición con `card.offsetLeft`, que en JavaScript es relativo al ancestro más cercano con `position` distinto de `static` (en este caso `.xh-carousel-wrap`, que lo tiene por los botones de flecha) — **no** relativo al contenido con scroll del carrusel mismo. Como `.xh-carousel-wrap` tiene un margen negativo que depende del ancho de la ventana (el truco de pantalla completa), ese desfase crecía con el ancho de pantalla: pequeño e imperceptible en celular, grande en escritorio — de ahí que solo se notara ahí.

**Corregido:** se reemplazó `card.offsetLeft` por un cálculo con `getBoundingClientRect()` (posición del borde de la tarjeta menos la posición del borde del carrusel, más el scroll actual) — mide la posición real dentro del contenido con scroll, sin depender de qué elemento ancestro tenga `position: relative`. Probado en 1280px de ancho: cada clic ahora mueve una tarjeta completa, ida y vuelta.

### Se quitó el snap nativo del navegador por completo (22 jul, madrugada)
El fix anterior (offsetLeft → getBoundingClientRect) se probó exitoso en el navegador de prueba, pero el usuario confirmó — cambiando de navegador y de computador — que en escritorio real seguía fallando (cada clic corría la imagen "un poquito" y nunca llegaba a Buñuelo), mientras que en celular sí funcionaba perfecto. Como el navegador de prueba no logró reproducir esto, no se pudo depurar más a fondo — así que se eliminó la variable en vez de seguir cazándola.

**Cambio:** se quitó `scroll-snap-type` del carrusel por completo, y la navegación por flechas/segmentos ya no usa `scrollIntoView()` (que deja que el navegador decida el punto final) — ahora calcula el píxel exacto de destino con la misma matemática de `getBoundingClientRect()` que ya se había verificado, y mueve el carrusel ahí directamente con `scrollTo()`. Esto saca por completo cualquier lógica de "alineación" del navegador de la ecuación — si esto seguía fallando, la próxima sospecha es algo más profundo (zoom del navegador, configuración de accesibilidad, o un extensión/config específica de las máquinas de prueba).

⚠️ **Sin confirmar todavía por el usuario en escritorio real** — pendiente de su próxima prueba.

### Causa de fondo real encontrada (22 jul, madrugada): no era un bug de código, era de espacio físico — más un servidor de desarrollo caído a mitad de sesión
Con un diagnóstico pedido directamente al usuario (clic programático + medición de `scrollLeft`), se confirmó: el paso entre tarjetas era consistente (~350px) pero el destino absoluto quedaba corto por ~39px — un desfase sistemático que no se pudo explicar con matemática de coordenadas. Al cambiar la navegación de "ir a una posición absoluta" (`scrollTo`) a "moverme el ancho de una tarjeta desde donde estoy" (`scrollBy`, relativo), se reprodujo el problema en el propio navegador de prueba por primera vez — lo que permitió depurarlo de verdad en vez de adivinar:

**La causa real:** en pantallas muy anchas, el carrusel (que se extiende a todo el ancho de la ventana) es tan ancho que 3 de las 4 tarjetas ya caben visibles al mismo tiempo — dejando solo ~370px de espacio real para hacer scroll, menos que el ancho de una sola tarjeta (~400px). No era un bug de cálculo: **físicamente no había más espacio para desplazar**, por eso el primer clic "se quedaba corto" y los siguientes no hacían nada — ya se había llegado al máximo posible. Confirmado visualmente: tras un clic, Buñuelo + Almojábana + Pandebono ya estaban los tres visibles a la vez.

**Corregido:** se le puso un límite al ancho máximo del carrusel (antes crecía sin límite con el ancho de la ventana) para que en pantallas ultra-anchas no se muestren casi todas las tarjetas de una vez, garantizando que siempre quede espacio real de scroll entre cada clic.

**Hallazgo aparte, importante:** a mitad de esta sesión el servidor `shopify theme dev` se cayó en silencio (sin ningún mensaje de error visible) — los cambios de código dejaron de sincronizarse a la tienda durante un tramo sin que quedara evidencia de ello hasta revisar el log completo. Se reinició. **Si en el futuro un cambio "no aparece" a pesar de guardarse, lo primero a revisar es si el proceso de `theme dev` sigue vivo**, no asumir que el código está mal.

### Último ajuste (22 jul, madrugada): Pandebono se veía pero nunca quedaba "seleccionado"
Con el problema de espacio ya resuelto, quedó un detalle: Pandebono (la última tarjeta) sí llegaba a verse completo, pero nunca se marcaba como la tarjeta activa (ni se resaltaba, ni se llenaba su segmento en la barra de progreso) — el usuario lo describió como "la foto se ve pero no se selecciona". Causa: el sistema que decide "cuál tarjeta está más cerca" compara por distancia, pero la posición ideal de la última tarjeta puede quedar más allá de lo que el scroll físicamente alcanza una vez llega a su tope — así que Almojábana (la penúltima) siempre ganaba por distancia, aunque Pandebono ya estuviera completamente visible.

**Corregido:** si el scroll ya llegó al principio o al final del todo, se usa esa posición límite directamente para decidir la tarjeta activa (primera o última), en vez de comparar distancias. Verificado con medición directa: `lastCardIsActive: true`, segmento de progreso al 100%, y confirmado visualmente en captura.

### Rediseño final de la navegación (22 jul, madrugada): de "posición ideal por tarjeta" a proporción del espacio real
El fix anterior (fijar la tarjeta activa en los extremos del scroll) resolvió que Pandebono nunca se seleccionara, pero expuso el problema de fondo: con el ancho comprimido, la posición "ideal" de **Almojábana también** quedaba fuera de lo que el scroll podía alcanzar — así que al hacer clic en "siguiente" desde Buñuelo, saltaba directo a Pandebono sin pasar por Almojábana.

**Solución de fondo:** se abandonó por completo la idea de calcular la posición "ideal" en píxeles de cada tarjeta. Ahora se divide el espacio real de scroll que existe (`scrollWidth - clientWidth`, sea cual sea) en partes iguales — una por producto — y tanto "cuál tarjeta está activa" como "a dónde ir al hacer clic" usan esa misma proporción. Cada producto tiene garantizado un tramo alcanzable del scroll, sin importar cuán comprimido esté el espacio disponible.

Probado ida y vuelta con clics programáticos + medición directa: 0→1→2→3 y 3→2→1→0, pasos parejos (217px cada uno), sin saltos, verificado también visualmente.

### Segunda tanda de la propuesta Ryze: foto anotada con callouts (22 jul, madrugada)
Construida la sección "La nostalgia como oportunidad" con el patrón de Ryze — layout de dos columnas (texto + foto), con la foto del Pandebono en Rosca ya existente en el tema y 3 callouts anotados (punto dorado + etiqueta) señalando: corteza dorada de queso, textura esponjosa por dentro, y "sabe a recién horneado aunque estaba congelado". No requirió fotos nuevas — reutiliza `xoc-pandebono.jpg`, ya cargado en el tema. En mobile la foto se apila arriba del texto.

### Pendiente (siguiente tanda de la propuesta Ryze)
- [ ] Foto anotada con callouts en la sección de nostalgia (requiere foto de branding).
- [ ] Grid de insumos con foto real de ingredientes (requiere fotos).
- [ ] Founder story con foto real de Marlen (espera b-roll).
- [ ] Prueba social / testimonios (espera clientes del piloto post-feria).

Ver también [brief](brief-pagina-wholesale-b2b.md), [copy](copy-pagina-wholesale.md) y [rol de Shopify](rol-de-shopify.md).
