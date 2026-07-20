# El rol de Shopify en la estrategia

## Estado actual (conexión en vivo)

La tienda Shopify de Xocolata ya está activa y conectada:

| | |
|---|---|
| Dominio | `gjkkyq-ac.myshopify.com` |
| Plan | Basic |
| Moneda | COP |
| Zona horaria | -05 (Colombia) |
| Cuenta | xocolatapremium@gmail.com |

El Shopify CLI local también está instalado y autenticado con esta misma cuenta (para desarrollo de tema/app si se necesita).

## Cómo cambió su rol: de canal principal a infraestructura de recompra

El plan arrancó como **B2C** con Shopify como canal principal de venta + contenido. Al redireccionarse el proyecto a **B2B** (ver [plan B2B y feria de Miami](../04-estrategia-b2b/plan-b2b-feria-miami.md)), Shopify se degrada como canal de conversión principal —el comprador B2B no hace checkout con tarjeta, negocia por WhatsApp— pero **no se elimina**: se reconvierte a tres funciones concretas.

### 1. Catálogo vivo y prueba de seriedad de marca
Sigue siendo la vitrina pública de Xocolata. Cuando un negocio busca la marca en Google antes de responder un correo o WhatsApp (siempre lo hace), debe encontrar algo serio.

### 2. Casa de la landing page de captación B2B
La página de aterrizaje de la Empanada de Cambray se monta **dentro de Shopify**, no en otra plataforma, porque:
- Todo vive en una sola dirección de internet (el dominio de Xocolata apunta ahí).
- La medición de visitas de Meta se acumula desde el día uno (abarata los anuncios de recordación más adelante).
- Cuando llegue la Fase 4, el portal de pedidos mayoristas queda en la misma casa donde el cliente ya conoció la marca.

Es la **Meta 1.5** del plan ejecutivo — ver [plan ejecutivo, OKRs e indicadores](../04-estrategia-b2b/plan-ejecutivo-okrs-e-indicadores.md) y la estructura completa de la landing en [guía comercial y plantillas](../04-estrategia-b2b/guia-comercial-y-plantillas.md#la-página-de-aterrizaje). ⚠️ Hay una inconsistencia de fecha entre documentos sobre cuándo se publica (31 jul vs. 5 ago) — ver [decisiones abiertas](../decisiones-abiertas.md).

### 3. Portal de re-orden B2B/Wholesale (Fase 4, post-cierre)
Activar **Shopify B2B/Wholesale** — precios ocultos por cliente aprobado — como portal de re-orden para aliados pequeños una vez cerrados por WhatsApp, así la recompra se automatiza sin fricción. Mínimo de compra: **1 caja**.

- El B2C (pocas ventas, pero sirven como evidencia de demanda ante distribuidores) sigue pasando por **Bosanet**.
- El cliente pide por Shopify, Bosanet despacha — pero "el cliente es nuestro": la base de datos queda en casa, no en Bosanet.
- Es la **Meta 4.4** del plan ejecutivo: portal de pedidos mayoristas funcionando, con los primeros aliados reordenando por su cuenta sin que haya que llamarlos.

## Resumen de la reconversión

> "Shopify pasa de 'canal de captación' a 'infraestructura de recompra y catálogo'."

La tienda al consumidor final pasa a segundo plano; la landing B2B será la portada.

## A futuro

Una segunda línea de materia prima/insumos, cuando se valide cómo sacar su FDA — y a futuro una página de ventas propia gestionada por Gustavo/Valentina por comisión (fase post-Bosanet). Ver nota sobre esta línea en [decisiones abiertas](../decisiones-abiertas.md).

Ver también [plan B2B y feria de Miami](../04-estrategia-b2b/plan-b2b-feria-miami.md) y [estrategia de contenido y ads](../05-contenido-y-marketing/estrategia-contenido-ads.md).
