# CLAUDE.md

Orientación para Claude Code al trabajar en este repositorio.

## Qué es este repo

Este es el "cerebro" del proyecto **Xocolata Food Premium**: una base de conocimiento en Markdown que organiza todo lo hablado y planteado sobre el negocio (estrategia B2B, producto, costos, marketing, feria de Miami, inversión). No es un sitio web ni contiene código — es documentación de negocio para que cualquier persona (o cualquier sesión de Claude) pueda entender el estado del proyecto sin tener que releer transcripciones de reuniones ni PDFs sueltos.

Empieza siempre por [00-resumen-ejecutivo.md](00-resumen-ejecutivo.md) para orientarte antes de responder preguntas sobre el proyecto.

## Relación con otras carpetas del proyecto

- **`../Datos Xocolata/`** — archivos fuente crudos (PDFs, imágenes de marca, capturas de WhatsApp, notas). No están versionados en este repo a propósito (deliberado por el usuario, para mantener el repo liviano). Cuando lleguen archivos nuevos ahí, hay que leerlos, extraer lo relevante y organizarlo en este repo — no copiar el archivo tal cual.
- **`../Shopify/`** — carpeta de trabajo con el Shopify CLI instalado y autenticado (cuenta xocolatapremium@gmail.com). Ahí se desarrolla el tema/la app de Shopify, si aplica.
- **Conector Shopify (MCP)** — hay un conector en vivo a la tienda `gjkkyq-ac.myshopify.com`. Úsalo para consultar o modificar productos, colecciones, pedidos, etc. en tiempo real; no dupliques ese estado como texto estático aquí salvo como snapshot puntual con fecha.

## Convenciones de este repo

- **Un tema, un archivo.** Antes de crear un archivo nuevo, revisa si el tema ya tiene uno (ver el mapa en [README.md](README.md)) y actualízalo en vez de duplicar.
- **Enlaces relativos entre archivos**, formato Markdown estándar (`[texto](ruta/archivo.md)`), no wikilinks. Cada archivo nuevo debería enlazar a los archivos relacionados al final ("Ver también...").
- **Gaps y contradicciones van a [decisiones-abiertas.md](decisiones-abiertas.md)**, no se resuelven inventando una respuesta. Si un documento nuevo resuelve algo que estaba ahí anotado, actualiza esa entrada (táchala o muévela a resuelto) en vez de dejarla huérfana.
- **Personas, empresas y contactos van a [personas-y-contactos.md](personas-y-contactos.md)** — no repitas biografías completas en cada archivo temático, solo referencia con link.
- **Fechas relativas → fechas absolutas.** Si una nota de reunión dice "el jueves" o "en 8 días", conviértelo a fecha absoluta antes de guardarlo, y anota la fecha de la reunión/fuente si es relevante para entender por qué esa fecha tiene sentido.
- **No borres historial sin razón.** Si un plan cambia, actualiza el archivo pero considera si vale la pena dejar una nota breve de "esto reemplaza X decisión anterior" cuando el cambio sea significativo — el historial de git ya guarda las versiones previas, así que no hace falta duplicar texto tachado dentro del archivo.
- **Español, tono directo.** Los documentos fuente están en español y así se mantiene este repo.
- **Etiquetado de huevo y lácteos:** en cualquier lista de ingredientes, ficha técnica o empaque, siempre "Huevo Pasteurizado" / "Mantequilla Pasteurizada" / "Queso Pasteurizado" — nunca el ingrediente solo. Ver [empaques y alérgenos](02-producto/empaques-y-alergenos.md).

## Cuando llegue información nueva

1. Léela completa (incluye PDFs e imágenes si aplica — usa el Read tool, que puede renderizar PDFs a imágenes si `pdftoppm`/poppler está disponible en el PATH del proceso).
2. Identifica en qué archivo(s) temático(s) encaja.
3. Actualiza esos archivos — no crees una carpeta nueva por cada reunión.
4. Si hay contradicciones con lo ya documentado, resuélvelas si la fuente nueva es claramente más reciente/autoritativa, o anótalas en decisiones-abiertas.md si no está claro.
5. Actualiza el resumen ejecutivo si el panorama general cambió.

## Qué NO va en este repo

- Credenciales, tokens o cualquier dato sensible de acceso.
- Archivos binarios (PDFs, imágenes) — quedan en `../Datos Xocolata/` sin versionar, por decisión explícita del usuario.
- Código de la tienda Shopify — eso vive en `../Shopify/`.
