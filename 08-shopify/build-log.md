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

### Tercera tanda de la propuesta Ryze: grid de insumos con fotos reales (29 jul)
Generadas las 4 fotos de ingredientes en ChatGPT (harinas, lácteos, arequipe, empaques — ver [imágenes de branding generadas](../01-marca/imagenes-branding-generadas.md#fotos-de-ingredientes--grid-de-insumos-29-jul-2026)), convertidas a JPG optimizado (~100-240 KB) y agregadas como nueva sección "Nuestra próxima etapa" entre "Por qué ser aliado" y "FAQ" en `xoc-home.liquid`: grid de 4 tarjetas (foto + título + beneficio corto), reusando las clases `.xh-grid`/`.xh-card` que ya existían en el CSS pero habían quedado sin usar tras el rediseño del carrusel. Incluye una nota explícita de que la línea de insumos es visión a largo plazo, no oferta activa — consistente con [línea de insumos y materias primas](../02-producto/linea-insumos-materias-primas.md). Verificado en desktop y mobile (apila a 1 columna).

### Cuarta tanda: video cinemagraph en la sección de nostalgia, primer uso de Higgsfield (29-30 jul)
Se conectó **Higgsfield AI** como herramienta de generación de video (CLI `@higgsfield/cli` + skills oficiales instalados vía `npx skills add higgsfield-ai/skills`, autenticado con `xocolatapremium@gmail.com`, plan Ultra). Es la vía recomendada para video de aquí en adelante — ChatGPT por navegador sigue siendo el camino correcto para fotos, pero no genera video.

Con la misma foto de `xoc-pandebono.jpg` que ya vive en el tema, se generó un cinemagraph de 5s (Seedance 2.0, image-to-video): cámara prácticamente fija con un empuje mínimo, el pandebono se mantiene sin deformarse, y solo unos hilos de vapor cálido se mueven de fondo. Verificado frame a frame antes de integrarlo — el pan no cambia de forma entre cuadros, solo el vapor. Aprobado por el equipo a la primera.

Reemplazado el `background-image` estático de `.xh-annotated__img` por un `<video autoplay muted loop playsinline>` posicionado encima (mismo contenedor, mismo `object-fit:cover`), con la foto original como `poster` y como fondo CSS de respaldo. Se oculta el video vía `prefers-reduced-motion:reduce`, dejando la foto estática como fallback accesible. El video de 4.3 MB que entrega Higgsfield se recomprimió con ffmpeg a ~600 KB (900×1200, CRF 23, sin audio, faststart) antes de subirlo a `assets/`. Los callouts existentes siguen funcionando sin cambios, ya que están posicionados sobre el contenedor, no sobre la imagen.

**Nota operativa:** durante esta sesión el proceso `shopify theme dev` volvió a caer en silencio (tercera vez documentada en este log) — reiniciado. Además, se detectó que tanto `shopify theme dev` como `npx skills add ...` requieren Node ≥22, mientras el Node por defecto del sistema es v20.14 — se usa `fnm` (ya instalado) para invocar esos comandos con Node 22 (`fnm use 22.23.2`) sin tocar la instalación global.

### Ajuste de callouts tras el video (30 jul)
Al revisar el cinemagraph, el callout "Corteza dorada de queso" quedó flotando sobre el fondo, sin tocar el pan. Causa real: `.xh-callout` centraba con `transform:translate(-50%,-50%)` el ancla en el **centro de toda la etiqueta** (punto + texto), así que entre más largo el texto, más lejos quedaba el punto visual del lugar que en realidad se quería señalar — no era un problema de encuadre del video. Corregido a `translateY(-50%)` únicamente (el punto ahora sí marca el `top`/`left` literal, sin importar el largo del texto) y reubicados los 3 callouts según los rasgos reales del video (corteza arriba, miga al centro, pieza frontal abajo-izquierda).

### Quinta tanda: "Se sienten en casa" + prueba social tentativa, adaptando el patrón "Supporting Everyday Wellness" de Ryze (30 jul)
Dos secciones nuevas en `xoc-home.liquid`, a pedido explícito del equipo tras revisar capturas de la página de Ryze:

**"Se sienten en casa"** (entre "La colección" y "Cómo funciona"): adapta la banda de tags de beneficio de Ryze ("Happiness Booster / Sharp Focus") a dos tags emocionales propios — **Sabe a casa** / **Nostalgia instantánea** — sobre una banda vinotinto con íconos dorados. Debajo, un panel de dos columnas "Sabor / Sensación" (equivalente a "Flavor / Feeling" de Ryze): checklist de sabor + párrafo de sensación, junto a la foto de `xoc-bunuelo.jpg` (arequipe derramándose) ya existente en el tema — no hizo falta generar ninguna imagen nueva. **Decisión deliberada:** no se agregaron badges tipo "Sin gluten" o "Sin conservantes" (el patrón de free-from claims de Ryze) porque la certificación gluten-free de Xocolata sigue sin confirmar con Daka (ver [empaques y alérgenos](../02-producto/empaques-y-alergenos.md)) — cualquier claim de ese tipo espera esa confirmación.

**Prueba social tentativa** (entre "Por qué ser aliado" e "Insumos"): builds el bloque #9 de la propuesta Ryze que seguía pendiente. Como no hay ningún testimonio real todavía, **no se inventaron citas atribuidas a negocios reales** — eso sería presentar contenido falso como genuino en un sitio comercial en vivo. En su lugar, la sección queda completamente construida y funcional (3 tarjetas: avatar con iniciales, cita, nombre de negocio + ciudad) pero cada tarjeta está marcada explícitamente como **"(ejemplo)"** junto al nombre, y hay una nota bajo el título aclarando que son ejemplos ilustrativos que se reemplazan por testimonios reales después de la feria de Miami. Formato B2B (negocio + ciudad + cita operativa) en vez del patrón de reseña individual de Ryze (estrellas + "verified buyer").

Verificado en desktop y mobile — ambas secciones apilan correctamente.

### Sexta tanda: foto de cafetería para "Se sienten en casa" — segundo uso de Higgsfield, esta vez para imagen (30 jul)
El equipo sintió que el panel "Se sienten en casa" quedó muy plano (foto de producto en estudio, mismo tratamiento que el resto del sitio) y pidió una escena de estilo de vida: una mesa de cafetería real con los productos servidos, para que un dueño de negocio se imagine el producto en su propio mostrador.

Se generó con **Higgsfield → GPT Image 2** (el mismo motor que ChatGPT, pero sin la fricción del navegador — costo real: 7 créditos sobre un saldo de ~2.785, prácticamente gratis). Primer intento: escena de cafetería correcta en ambiente/luz, pero el modelo reinterpretó la forma del Pandebono y el Buñuelo en vez de respetar el producto real. **Corregido pasando las fotos reales (`xoc-pandebono.jpg`, `xoc-bunuelo.jpg`) como `--image_references`** para que el modelo copie la forma/textura exacta en vez de improvisar — funcionó a la segunda. Una tercera ronda ajustó el relleno del buñuelo a **solo arequipe** (sin mermelada) y bajó un poco el tamaño de los pandebonos en el encuadre. Aprobada por el equipo en la tercera versión.

**Rediseño de la sección:** la foto pasó de ser una imagen pequeña al lado del panel de texto a ser la **protagonista** — banner de 16:9 a todo el ancho del contenido, con el panel "Sabor/Sensación" debajo (antes iban lado a lado). Nuevas clases `.xh-flavor-hero` (reemplaza `.xh-flavor`/`.xh-flavor__img`) y `.xh-flavor-panel` (reemplaza `.xh-flavor__panel`). En mobile la foto cambia a 4:3 para no recortar tanto. También se ajustó el copy de "Sensación" a pedido del equipo, cambiando el cierre de "vuelta en la cocina de su abuela" a "vuelta en casa" — más directo, coincide con el título de la sección.

**Nota de herramienta:** el tema usa un contenedor interno `.page-wrapper` con su propio scroll (no `window`/`body`) en viewports de escritorio — hay que hacer scroll ahí, no en `window`, al depurar visualmente con capturas automatizadas. En mobile sí vuelve a ser el `body` normal.

### Séptima tanda: prueba social más completa, inspirada en los reviews de Ryze (30-31 jul)
El equipo pidió que la sección de testimonios se viera "tan completa como los de Ryze" (fotos + texto convincente), pero con un límite explícito: **no generar fotos de rostros de personas** para acompañar citas de negocios inventados — un texto marcado "(ejemplo)" ya es honesto por sí solo, pero ponerle una cara de IA a un nombre de negocio ficticio cruza a presentar una identidad falsa como real. Se optó por una alternativa sin ese riesgo: 3 fotos genéricas de interiores de negocio (mostrador de panadería, bodega de distribución, mostrador de cafetería — generadas en Higgsfield/GPT Image 2, sin personas, sin letreros ni marcas) en vez de un rostro.

Rediseñada cada tarjeta: foto de negocio (16:9) con badge "Aliado verificado" superpuesto, 5 estrellas doradas (SVG), cita más larga y específica orientada al *significado* de trabajar con Xocolata (no solo beneficios operativos), nombre + ciudad + "(ejemplo)" se mantiene. Las 3 citas nuevas:
- Panadería El Trigal (Miami, FL): ser los primeros con el sabor de Colombia cambió cómo los ven sus clientes.
- Distribuidora Andina (Houston, TX): la garantía Triple Sello cumplida generó confianza en el resto de la relación.
- Café Latino Express (Newark, NJ): el impacto emocional de ver a un cliente reaccionar al primer bocado.

Verificado en desktop y mobile.

### Octava tanda: foto de empaques reales con producto, a partir del diseño final de Daka (31 jul)
El equipo subió el diseño de empaque final y listo para imprimir de los 4 productos (`Material grafico/branding-generado/XOCOLATA X4 REF.pdf`, ver [empaques y alérgenos](../02-producto/empaques-y-alergenos.md) para los hallazgos de esa revisión) y pidió generar una foto de producto real usando esos empaques — para reemplazar la imagen genérica de rollos de plástico sin marca que tenía la tarjeta "Empaques y soporte" del grid de insumos.

Las páginas del PDF (formato de imprenta, con anotaciones de medidas) se convirtieron a imagen con `pdftoppm` (Poppler, ya instalado) y se recortó el panel frontal de cada bolsa. Esos recortes, más las fotos reales de Empanada de Cambray y Pandebono en Rosca, se pasaron como `--image_references` a Higgsfield/GPT Image 2 para generar un render 3D fotorrealista de las dos bolsas reales de pie sobre mármol oscuro, con el producto correcto visible en cada ventana — mismo tratamiento visual que el resto de fotos de insumos. Salió bien a la primera. Reemplaza `assets/xoc-insumo-empaques.jpg`.

**Nota de continuidad de sesión:** a mitad de esta tanda la sesión se cortó (el proceso `shopify theme dev` y el estado del navegador se perdieron, igual que en otras ocasiones documentadas en este log). Los 4 trabajos de Higgsfield en curso en ese momento (3 fotos de testimonios de la séptima tanda + esta foto de empaques) **sí habían terminado del lado del servidor** — se recuperaron con `higgsfield generate list --json` en vez de regenerarlos, sin gastar créditos de más. Confirma que los jobs de Higgsfield son seguros de retomar así tras un corte: no hace falta reiniciarlos si ya se lanzaron.

### Novena tanda: footer a medida (31 jul)
El footer seguía siendo el bloque genérico de Shopify (título + un párrafo, sin estilo de marca, sin navegación). Se construyó `sections/xoc-footer.liquid` — sección nueva e independiente (no vive dentro de `xoc-home.liquid`, porque el footer se renderiza en `footer-group.json`), con la misma paleta vinotinto/dorado y tipografía serif del resto del sitio: columna de marca (wordmark + tagline + Cali, Colombia), columna "Explorar" con anclas a las secciones del home, columna "Hablemos" (correo + fecha de la feria + botón CTA), y una barra inferior con el sello Triple Sello + copyright. `footer-group.json` se actualizó para usar `"type": "xoc-footer"` en vez del bloque genérico, dejando `footer-utilities` (copyright automático + links de políticas) intacto debajo.

Se agregaron IDs de ancla a 4 secciones de `xoc-home.liquid` que no los tenían (`#xh-como-funciona`, `#xh-insumos`, `#xh-faq`, `#xh-contacto`) para que los enlaces del footer funcionen — solo `#xh-coleccion` ya existía, del carrusel. Verificado en desktop y mobile, y confirmado que el ancla navega al lugar correcto.

### Décima tanda: fotos de proceso para "Cómo funciona" (31 jul)
Era la única sección del home que seguía siendo puro texto (3 pasos numerados sin ninguna imagen), mientras el resto del sitio ya tenía foto o video en cada sección. Se generaron 3 fotos en ChatGPT (no Higgsfield esta vez, a pedido del equipo), mismo sistema visual de marca, contando el proceso con el Pandebono en Rosca como hilo conductor:
- **Recibes:** el pandebono congelado, con escarcha y niebla fría azulada.
- **Horneas:** el pandebono dorándose dentro de un horno con la puerta entreabierta, luz cálida intensa.
- **Vendes:** varios pandebonos recién horneados en vitrina de panadería.

Cada paso ahora tiene su foto (proporción 1:1, esquinas redondeadas, sombra) con el número flotando en la esquina superior en un badge translúcido, encima del texto que ya existía. Clases nuevas `.xh-step__img`/`.xh-num--onphoto`, sin tocar `.xh-steps`/`.xh-step` compartidas con la sección de Triple Sello (que sigue igual, verificado). Verificado en desktop y mobile.

**Corrección de textura (31 jul, mismo día):** el equipo regeneró las 3 fotos con la corteza del Pandebono **lisa** en vez de la textura moteada/rugosa que salió en la primera ronda — más fiel al producto real. Reemplazadas con los mismos nombres de archivo. Al probar el cambio, la vista previa del navegador siguió mostrando las fotos viejas incluso después de reiniciar `shopify theme dev` — se confirmó con un fetch directo a la URL del asset (`cache: 'no-store'`) que el servidor ya tenía el archivo correcto; era únicamente el pintado/caché de la pestaña del navegador de prueba, resuelto con un `location.reload(true)`. **Nota para el futuro:** si un archivo remplazado con el mismo nombre "no cambia" en la vista previa, antes de sospechar del servidor o de `theme dev`, verificar el asset directo con fetch/`cache: no-store` — casi siempre es la pestaña, no el archivo.

### Ajuste visual: insignias de la fila de atributos (31 jul)
Los 4 atributos (-18°C, 8 MIN HORNO, HUEVO PASTEURIZADO, PRODUCTO COLOMBIANO) debajo de los pasos de "Cómo funciona" se sentían poco definidos — solo un ícono delgado flotando junto al texto, sin ningún fondo. Se envolvió cada ícono en una insignia circular con relleno degradado dorado y borde, y cada atributo completo pasó a ser una tarjeta con fondo sutil y borde — mismo lenguaje visual que el resto del sitio (círculos dorados de `.xh-num`, tarjetas translúcidas). Se agregó también un efecto sutil de elevación al pasar el mouse. Verificado en desktop y mobile.

### Redes sociales en el footer (31 jul)
Agregados los 3 íconos de redes sociales (TikTok, Instagram, Facebook) en `xoc-footer.liquid`, debajo de "Cali, Colombia" en la columna de marca — mismas insignias circulares doradas que ya se usan en la fila de atributos de "Cómo funciona", abren en pestaña nueva (`target="_blank" rel="noopener"`). Enlaces reales:
- TikTok: https://www.tiktok.com/@xocolatafoodpremium
- Instagram: https://www.instagram.com/xocolatafoodpremium
- Facebook: https://www.facebook.com/profile.php?id=61591942831611

Verificado en desktop y mobile.

### Limpieza de la fila de atributos (31 jul)
Se quitó "Huevo Pasteurizado" de la fila de atributos de "Cómo funciona" — era un dato de ingrediente/inocuidad mezclado entre datos de proceso y logística (-18°C, 8 MIN HORNO, PRODUCTO COLOMBIANO), se sentía fuera de tono. Quedan los 3 que sí cuentan una historia coherente de principio a fin. El dato de pasteurización sigue disponible en otras partes del sitio (ej. "Respaldo de exportación") y en la ficha técnica cuando se redacte.

### Comparativa vs. proveedor típico en "Por qué ser aliado" (31 jul)
El equipo pidió convertir las 4 tarjetas de texto de "No vendemos congelados. Construimos aliados." en una comparación directa contra el proveedor congelado típico del mercado — más persuasivo que 4 bullets sueltos. Se reformuló el mismo copy ya validado (portafolio, cocina, territorio, respaldo) en formato de tabla de 2 columnas: "Proveedor congelado típico" (gris, con ✕) vs. "Xocolata" (resaltado en dorado, con ✓), 4 filas. En mobile se apila por dimensión (nombre de la fila → ✕ típico → ✓ Xocolata) en vez de tabla, para que siga siendo legible.

Reemplaza `.xh-grid--4txt`/`.xh-tile`, que quedaron sin uso — se limpiaron esas reglas CSS y sus referencias en los media queries compartidos con `.xh-grid`/`.xh-steps`. Verificado en desktop y mobile.

**Ajuste (mismo día):** el equipo no quería que la tabla se "reacomodara" en celular perdiendo la forma de tabla — pidió que se viera igual, tipo tabla, en cualquier tamaño. Se cambió el enfoque: en vez de reflow a una columna en mobile, la tabla mantiene sus 3 columnas siempre (`min-width:660px`) dentro de un contenedor con scroll horizontal (`.xh-vs-scroll`), con una pista de texto "Desliza para ver la comparación completa →" visible solo en mobile. Confirmado que el scroll lateral funciona y revela la columna de Xocolata completa.

**Rediseño completo (mismo día):** el equipo mostró una referencia de una tabla comparativa de otra marca ("Geli vs Otros") con un formato distinto y más limpio — una sola columna de texto de beneficio por fila, con solo un check/x grande en columnas de ícono para cada competidor, encabezado oscuro con los nombres, badge "Recomendado" flotante, y filas con franjas alternas. Se reconstruyó la tabla completa (`.xh-vs2`, reemplaza `.xh-vs`/`.xh-vs-scroll` de la iteración anterior) siguiendo ese patrón en la paleta vinotinto/dorado: encabezado vino con "Xocolata"/"Otros", badge dorado "Recomendado", 4 filas de beneficio (mismo copy ya validado, reformulado como afirmación positiva), check dorado circular para Xocolata y X gris para Otros. Como ahora solo hay un texto largo por fila (no dos), la tabla ya no necesita scroll horizontal en mobile — el texto simplemente hace wrap y las columnas de ícono se angostan un poco vía media query. Verificado en desktop y mobile.

### Ticker con íconos, inspirado en Ryze (31 jul)
El equipo recordó que la cinta scrolleable de Ryze no es solo texto — cada frase lleva un ícono pequeño delante (visto en vivo en ryzesuperfoods.com para confirmar antes de construir, no se adivinó). Se rehizo `.xh-ticker` de Xocolata con el mismo patrón: un ícono de línea (ya usados en el resto del sitio, mismo lenguaje visual) antes de cada una de las 5 frases — reloj (8 min horno), escudo (Triple Sello), bandera (territorio), casa (tradición colombiana), globo (calidad global) — con un separador vertical entre cada una en vez de "·". Estructura HTML cambiada de un string largo con `&nbsp;·&nbsp;` a un `{% capture %}` con 5 `<span>` reales (más fácil de mantener), duplicado dos veces para el loop continuo sin corte, igual que antes. Verificado en desktop y mobile.

### Habilitar inglés de verdad: Shopify Markets + selector de idioma (31 jul)
Todo el copy bilingüe ya estaba escrito en el tema (`{% if en %}...{% else %}...{% endif %}` en cada sección), pero `/en` colapsaba silenciosamente a la raíz en español — el idioma inglés estaba "publicado" en `shopLocales` pero no era **enrutable**: en Shopify, publicar una traducción no basta, hace falta que un Market tenga una "web presence" que incluya ese locale.

Diagnóstico vía GraphQL Admin:
- `shopLocales`: `en` publicado (no primario), `es` primario y publicado — la traducción sí existe.
- El único Market de la tienda ("Colombia", condición región = solo `CO`) tenía `webPresence: null` — sin ruta configurada para ningún locale alterno.
- La consulta `webPresences` (a nivel de tienda, no de mercado) reveló que **ya existía** una web presence huérfana en el dominio principal (`defaultLocale: es`, `alternateLocales: []`, sin ningún mercado asociado) — probablemente creada automáticamente al activar el idioma inglés en el admin, pero nunca completada.

Solución (2 mutaciones, sin tocar condiciones de mercado ni checkout):
1. `webPresenceUpdate` sobre esa web presence existente, agregando `en` a `alternateLocales`.
2. `marketUpdate` sobre el mercado "Colombia", con `webPresencesToAdd` apuntando a esa web presence.

**Punto clave:** esto **no crea un mercado nuevo de Estados Unidos ni toca las condiciones del mercado Colombia** (que sigue restringido a `CO`). Solo agrega el ruteo `/en/` sobre el dominio existente. Respeta la restricción legal del [brief](brief-pagina-wholesale-b2b.md) — "el checkout no debe estar activo hacia clientes de EE. UU. todavía" — porque no se habilitó ningún mercado ni moneda para EE. UU., solo la ruta de idioma.

Verificado en vivo: `/en` carga todo el sitio traducido (hero, ticker, colección, comparativa, FAQ, footer — todo). Además, el tema (Horizon) ya trae un selector de idioma nativo en el header (`show_language: true` en `header-group.json`), que antes no aparecía porque solo había un idioma disponible — en cuanto `en` quedó enrutable, el dropdown "Español ▾" apareció solo en el header, sin escribir código nuevo. Probado clic/selección real en el navegador: cambia todo el sitio a inglés al instante, mismo diseño, conservando la página actual. Verificado en desktop.

### Páginas de detalle de producto, las 4, bilingües (31 jul)
Hasta ahora los 4 productos usaban la plantilla genérica de Shopify (galería + caja de compra con "Agregar al carrito" y precio $0,00 — rota para el modelo de cotización B2B). Se construyó una página a medida por producto, mismo patrón visual del resto del sitio (paleta vino/dorado, `{% if en %}` bilingüe): `sections/xoc-product-empanada.liquid`, `xoc-product-bunuelo.liquid`, `xoc-product-almojabana.liquid`, `xoc-product-pandebono.liquid`, cada una con su `templates/product.[handle].json` y asignada al producto vía `templateSuffix` (GraphQL `productUpdate`). Estructura común, definida primero en Empanada de Cambray y replicada en las otras 3:

1. **Hero** — foto real del producto (reusa los assets ya existentes del home), eyebrow, tagline y pitch ya validados (mismo copy del carrusel del home), CTA "Hablemos" (mailto) en vez de botón de compra — sin precio, sin carrito, consistente con el modelo de cotización.
2. **Cómo viene tu pedido** — 4 tarjetas estadísticas (peso por unidad, unidades por paquete/bolsa, paquetes/bolsas por caja, total por caja), mismos números ya usados en las tarjetas del home.
3. **Preparación** — banda vino con -18°C / 8 MIN HORNO / PRODUCTO COLOMBIANO, más una línea de horno explícita: **precalentar a 180°C, ~8 minutos, sin descongelar** (dato pedido directo por el equipo, igual para los 4 productos).
4. **Ingredientes y alérgenos** — texto real tomado del panel nutricional del empaque final (`XOCOLATA X4 REF.pdf`), no inventado, con tabla de información nutricional (calorías, grasa, sodio, carbohidratos, proteína) también real.
5. **Cross-sell** — tarjetas a los otros 3 productos de la colección.
6. **CTA final**.

**Hallazgo importante de alérgenos (corrige el brain):** al leer el panel nutricional real, resultó que **la Empanada de Cambray usa harina de maíz (no de trigo)** y declara solo "Contiene: Leche" — no lleva gluten, al contrario de lo que decía este documento hasta hoy. La única de los 4 productos que sí lleva harina de trigo y declara "Contiene: Leche y gluten" es la **Almojábana Especial** — queda marcado explícitamente en su página. Ningún producto lleva un sello "Gluten Free" (la certificación formal con Daka sigue pendiente), solo se muestran los ingredientes tal como están impresos. Ver corrección aplicada en [empaques y alérgenos](../02-producto/empaques-y-alergenos.md).

**Ajustes de datos, a pedido del equipo:**
- El peso de la Empanada quedó en **60 g** (el ya validado en el resto del sitio), aunque el panel nutricional impreso dice 80 g — se mantuvieron los valores nutricionales reales (240 cal, etc.) con la etiqueta de porción en 60 g para no contradecir el resto del sitio.
- Pandebono en Rosca: el ingrediente del empaque real dice "mantequilla" y "leche" sin el calificativo "pasteurizada" (inconsistencia ya flagged en el 31 jul). En el sitio web sí se aplicó el calificativo correcto ("mantequilla pasteurizada", "leche pasteurizada"), siguiendo la convención del 21 jul que exige esto en toda pieza de cara al cliente incluyendo la web — el empaque impreso sigue pendiente de que Daka lo corrija.

**Bloqueo encontrado y resuelto:** los 4 productos estaban en estado Borrador (`DRAFT`), no publicados al canal de Tienda Online — cualquier URL de producto daba 404 incluso en la vista previa del tema. No es algo introducido en esta tanda, ya existía. Se confirmó con el equipo que esto no afecta el modelo de cotización (el precio sigue en $0, sin checkout real) y se publicaron los 4 (`productUpdate` a `ACTIVE` + `publishablePublish` al canal Tienda Online).

Verificado en vivo: los 4 productos cargan correctamente en desktop y mobile, en español e inglés.

### Logo real subido al header y favicon (31 jul)
El header seguía mostrando el nombre de la tienda como texto plano ("Mi tienda") porque nunca se había subido ningún logo — pendiente desde el brief original. Se compararon 3 candidatos con el equipo (ver comparación visual): un monograma "X" suelto, un lockup generado con IA para fondo claro (nunca usado en producción), y **el logo real ya aprobado e impreso en el empaque final de Daka** (`XOCOLATA X4 REF.pdf`). Se eligió el tercero — es el único que ya pasó por aprobación de producción real; usar cualquier otro en la web crearía una discrepancia entre lo que el cliente ve en la página y lo que recibe en la caja física.

Proceso técnico: se extrajo el lockup del arte final (recorte de alta resolución del panel frontal del empaque), se limpió el fondo vino con `ffmpeg colorkey` para dejarlo transparente (funciona tanto en el header claro como sobre fondos oscuros), y se recortó por separado solo la "X" caligráfica para el favicon (el lockup completo no se lee a 32px). Ambos archivos se subieron a Shopify vía la API (`stagedUploadsCreate` + `fileCreate`) y se referenciaron en `config/settings_data.json` (`settings.logo`, `settings.favicon` — son ajustes nativos del tema Horizon, no assets de tema). Verificado: el logo carga en el header (90×44px) y el favicon en la pestaña (32×32px, recortado).

**Pendiente, no se pudo hacer por API:** el nombre de la tienda (`shop.name`, sigue en "Mi tienda") no es editable vía GraphQL Admin API por diseño de Shopify — hay que cambiarlo manualmente en el admin (Configuración → General). Es un cambio de 1 minuto para el equipo.

### Dos bugs de mobile reportados y corregidos (31 jul)
El equipo reportó, probando en celular real: (1) al abrir el menú hamburguesa desde el hero, la cinta dorada del ticker aparecía encima del panel del menú; (2) en la cuadrícula de productos, 3 de los 4 productos mostraban cuadros vacíos en vez de foto.

1. **Cinta sobre el menú:** `.xh-ticker` tenía `z-index:40` (heredado de cuando era solo un elemento sticky sin overlays alrededor). El panel del menú móvil del tema Horizon usa `z-index:18` (y su fondo oscuro `z-index:16`) — al ser la cinta `position:sticky`, con un z-index mayor quedaba visualmente por encima del menú abierto aunque estuviera "detrás" en el DOM. Bajado a `z-index:10`, confirmado en vivo que el menú ahora tapa la cinta correctamente.
2. **Cuadros vacíos en productos:** Empanada de Cambray, Buñuelo Relleno y Almojábana Especial nunca tuvieron una imagen subida al registro nativo de producto de Shopify (`featuredImage: null`) — solo Pandebono la tenía, de una sesión anterior. El carrusel del home no lo mostraba porque usa fotos hardcodeadas en el tema (`asset_url`), pero cualquier vista que use el sistema nativo de Shopify (cuadrícula de la colección `/collections/all`, recomendaciones "también te puede interesar") sí depende de esa imagen y salía en blanco. Se subieron las mismas 3 fotos ya usadas en el resto del sitio directamente al registro de cada producto vía la API (`stagedUploadsCreate` + `productCreateMedia`). Verificado en vivo: los 4 productos ya muestran foto en la cuadrícula de la colección.

### Pendiente (siguiente tanda de la propuesta Ryze)
- [ ] Founder story con foto real de Marlen (espera b-roll).
- [ ] Reemplazar los 3 testimonios de ejemplo por citas reales (espera clientes del piloto post-feria).
- [ ] Pedir a Daka que corrija las instrucciones de preparación del empaque impreso (dicen "waffles", placeholder no actualizado) y agregue "Pasteurizada" a mantequilla/leche del Pandebono.
- [ ] Confirmar con el equipo/Daka el peso real de la Empanada de Cambray (60 g usado en el sitio vs. 80 g del panel nutricional impreso).
- [x] ~~Cambiar el nombre de la tienda a "Xocolata Food Premium" en el admin~~ — hecho por el equipo (31 jul), verificado vía API (`shop.name`) y en vivo (pestaña del navegador).
- [ ] Número de WhatsApp comercial (sigue sin confirmar — todos los CTA "Hablemos" usan `mailto:` por ahora).

### Cinemagraph en el hero (31 jul)
El hero seguía siendo la única sección grande del home sin ningún tipo de movimiento (video/cinemagraph), mientras nostalgia e insumos ya lo tenían. Se usó la misma técnica ya validada del cinemagraph del pandebono (Higgsfield, Seedance 2.0, image-to-video, cámara fija) mismo sobre `xoc-hero.jpg` — foto que ya tenía vapor pintado de fondo, candidata ideal. Prompt: cámara estática sin movimiento, el pan sin deformarse, solo los hilos de vapor del fondo se mueven. Verificado frame a frame (1 por segundo, 5s totales): el pan es idéntico en todos los frames, solo cambia la forma del vapor. Aprobado a la primera.

Integrado en `.xh-hero` como `<video autoplay muted loop playsinline>` posicionado absoluto, con la foto estática de siempre como `poster`/fallback y respetando `prefers-reduced-motion` (oculta el video, deja la foto fija). El degradado de texto que antes iba pintado en el `background-image` se separó a su propio overlay (`.xh-hero__overlay`) para que quede encima del video sin taparlo. Verificado en vivo: el video hace loop correctamente en desktop y mobile.

### Barra superior con ícono y countdown en vivo, inspirada en Ryze (31 jul)
El equipo pidió, viendo la versión mobile de ryzesuperfoods.com, replicar su barra superior de anuncio: ícono + texto + countdown en vivo (verificado en el sitio real antes de construir). La barra de Xocolata era hasta ahora el bloque genérico de anuncio de Shopify (solo texto plano, sin ícono ni countdown). Se reemplazó por una sección a medida, `sections/xoc-topbar.liquid` — sello/escudo dorado + "Agenda tu degustación antes de la feria de Miami" + countdown compacto en línea (`44d 13h 48m 25s`), en `header-group.json` en el mismo lugar donde vivía el bloque genérico.

Reutiliza el mismo patrón de countdown ya construido para la sección "Countdown feria" del home (`data-xh-countdown`/`data-target`), pero como la barra vive en el grupo de header (aparece en **todas** las páginas, no solo el home), el script de countdown se duplicó dentro de la propia sección con una bandera `data-xtb-init` para evitar que se inicialice dos veces en la página de inicio (donde coexisten la barra superior y la sección de countdown más abajo). Verificado en vivo: el countdown corre en tiempo real (los segundos bajan) en desktop, mobile, home y páginas de producto.

### Foto base del hero cambiada a empaques reales, inspirada en Ryze (31 jul)
El equipo revisó ryzesuperfoods.com en modo celular y notó que su hero es 100% empaque de producto (bolsas paradas sobre una superficie estilizada), lo opuesto a lo que tenía Xocolata (comida servida sin empaque visible). Se decidió reconstruir la foto del hero alrededor del empaque real aprobado, en vez de la foto de producto suelto.

La foto se generó en ChatGPT (misma conversación "Xocolata Brand" usada para todo el branding previo, por consistencia), con el PDF real del empaque (`XOCOLATA X4 REF.pdf`) cargado como referencia de diseño/medidas, especificando el color correcto de la bolsa (`#7A1833`, sombras `#5C1226`, luces `#A82B4A`) para no repetir el error de tono más oscuro de versiones anteriores. Composición: 2 bolsas (Empanada de Cambray + Pandebono en Rosca) de pie sobre mármol oscuro, formato horizontal 16:9, con el lado izquierdo de la imagen más oscuro/despejado para sobreponer el texto del hero.

**Corrección de textura en la misma sesión:** la primera versión mostró la empanada con corteza hojaldrada/rugosa en la ventana transparente — inconsistente con la masa real (almidón de yuca + harina de maíz, sin trigo), que debe ser lisa como el pandebono. Se pidió la corrección puntual (solo textura, sin tocar composición/color/mármol) y quedó resuelta a la segunda vuelta.

Reemplaza `assets/xoc-hero.jpg` (mismo nombre de archivo, no requirió cambios de código) y se regeneró el cinemagraph de vapor (misma técnica Higgsfield/Seedance 2.0 ya validada) sobre la foto nueva — el vapor ahora sube detrás de las bolsas y en las luces cálidas desenfocadas del fondo, en vez de sobre comida servida. Verificado frame a frame y en vivo. Archivo fuente completo archivado en `Material grafico/branding-generado/xoc-brand-22-hero-empaques.png`.

### Fotos de los 4 productos regeneradas con investigación real previa (31 jul)
Las 4 fotos de producto (`xoc-empanada.jpg`, `xoc-pandebono.jpg`, `xoc-bunuelo.jpg`, `xoc-almojabana.jpg` — usadas tanto en el carrusel del home como en cada página de detalle de producto) tenían errores de realismo: la empanada se veía como hojaldre de trigo clásico (con repulgue trenzado), el pandebono tenía superficie craquelada, y no había forma de saber que la almojábana es más pequeña que los demás productos.

Antes de generar, se investigó cómo es cada producto realmente (búsqueda web, no se adivinó):
- **Empanada de Cambray**: receta tradicional del Valle del Cauca — masa de queso costeño y almidón de yuca (sin trigo), forma de media luna, masa lisa, relleno de dulce de guayaba y queso.
- **Buñuelo Relleno**: a diferencia de la empanada y el pandebono, el buñuelo SÍ debe verse craquelado/agrietado — es masa frita, no horneada, así que esa textura es auténtica. Relleno de arequipe y queso mozzarella inyectado después de freír.
- **Almojábana Especial**: tamaño real "pelota de golf" antes de hornear — debe verse claramente más pequeña que el pandebono o el buñuelo, disco aplanado, no bola grande.
- **Pandebono en Rosca**: confirma lo ya sabido — rosca lisa y dorada, sin agrietado.

Las 4 se regeneraron en la misma conversación de ChatGPT ("Xocolata Brand"), mismo mármol oscuro y luz cálida de marca. Reemplazan los archivos de tema con el mismo nombre (sin cambios de código) y ya están verificadas en vivo en el carrusel del home y en las páginas de producto.

**Actualización (mismo día):** el equipo notó que el menú móvil (que usa las imágenes nativas de producto de Shopify, no los assets del tema) seguía mostrando las fotos viejas — una de ellas ni siquiera era comida, era la foto de empaque de una ronda anterior. El MCP de Shopify se había desconectado a mitad de sesión (mismo tipo de corte que el servidor de tema); el equipo lo reconectó desde el panel de Conectores de la app de escritorio. Con la conexión restaurada, se subieron las 4 fotos nuevas como imagen nativa de cada producto (`stagedUploadsCreate` + `productCreateMedia`) y se eliminaron las imágenes viejas (`productDeleteMedia`, incluidas las 2 que tenía Pandebono). Verificado en vivo en el menú móvil de productos destacados: los 4 muestran ya la foto correcta.

### Foto de empaque individual en la sección "Cómo viene tu pedido" de cada producto (31 jul)
El equipo pidió una foto de cada producto ya dentro de su bolsa real, para que el comprador B2B vea exactamente cómo llega el pedido — hasta ahora esa sección solo tenía las tarjetas de datos (gramaje, unidades por bolsa/caja) sin ningún apoyo visual. Se generaron las 4 fotos en la misma conversación de ChatGPT ("Xocolata Brand"), con el PDF real del empaque (`XOCOLATA X4 REF.pdf`) y la foto del hero como referencia, usando el color de marca correcto de la bolsa (`#7A1833`, sombras `#5C1226`, luces `#A82B4A`) — bolsa de pie sobre mármol oscuro con la ventana transparente mostrando el producto real de cada referencia (misma investigación de textura ya documentada arriba: empanada y pandebono lisos, buñuelo craquelado, almojábana visiblemente más pequeña).

**Incidente:** la primera descarga de la foto del Buñuelo llegó corrupta (5.6 KB, en realidad una página de error HTML en vez de la imagen — detectado al leer el archivo, que no reconoció ningún formato de imagen válido). El equipo volvió a descargarla desde la misma conversación y la segunda vez sí llegó correcta (2 MB, textura craquelada visible).

Las 4 fotos (`xoc-empanada-empaque.jpg`, `xoc-pandebono-empaque.jpg`, `xoc-bunuelo-empaque.jpg`, `xoc-almojabana-empaque.jpg`) se agregaron como assets nuevos del tema y se insertaron en la sección "Cómo viene tu pedido" (`id="xpd-caja"`) de las 4 páginas de producto (`sections/xoc-product-*.liquid`), en un layout de dos columnas: foto del empaque a la izquierda, tarjetas de datos a la derecha (en mobile se apilan, foto arriba). Verificado en vivo en las 4 páginas, desktop y mobile.

Ver también [brief](brief-pagina-wholesale-b2b.md), [copy](copy-pagina-wholesale.md) y [rol de Shopify](rol-de-shopify.md).
