# ZEROPELO — Contexto completo del proyecto

> **Si eres un asistente leyendo esto por primera vez:** este documento es el punto de
> entrada. Contiene de dónde viene el proyecto, qué se ha hecho, qué decisiones se
> tomaron y por qué, y qué queda pendiente. Lee entero antes de proponer nada.
>
> **Última actualización:** 2026-08-27 (tarde)

---

## 1. Qué es esto

Una tienda de producto único de dropshipping, dirigida al mercado español.
Vende un **rodillo quitapelos reutilizable para perros y gatos** bajo la marca ZEROPELO.

| | |
|---|---|
| **Tienda en vivo** | https://alexghost1.github.io/zeropelo/ |
| **Repositorio** | https://github.com/alexghost1/zeropelo |
| **Proyecto local** | `~/Projects/tienda-nocturna` (Mac del propietario) |
| **Estado** | Escaparate terminado. **No puede cobrar todavía.** |
| **Inversión hasta hoy** | 0 € |

**Es un negocio separado** de la actividad principal del propietario, que es asesor
financiero. No deben mezclarse las dos identidades públicas ni sus datos.

---

## 2. De dónde viene

Nació el 26 de agosto de 2026 de un encargo de ejecución autónoma: investigar un
producto ganador, encontrar proveedor asiático, generar creatividades y desplegar una
tienda, todo con 0 € y sin intervención humana.

El plan original se auditó y se reescribió antes de ejecutarlo, porque cuatro cosas no
encajaban con la realidad del entorno. Están documentadas en `PLAN_PERFECCIONADO.md`
del proyecto local, y resumidas en la sección 6 de este documento.

---

## 3. El producto

**Rodillo quitapelos adhesivo con tapa transparente y rollo reemplazable.**

> ⚠️ **Corrección del 27/08/2026.** Durante los dos primeros días se trabajó sobre una
> suposición equivocada: se creía que era un rodillo de cámara reutilizable «sin
> recambios». **No lo es.** Lleva rollo adhesivo que se cambia. Toda la comunicación que
> afirmaba lo contrario se retiró el mismo día por ser publicidad engañosa.

**Especificaciones del fabricante:** ABS + PC + TPR · 19,5 × 11 × 6,5 cm · 160 g ·
botón PUSH para cambiar el rollo · blanco con detalles naranja y tapa transparente ·
para ropa, muebles, sofás, camas y asientos de coche.

**Precios:** 34,99 € el rodillo · 44,99 € el kit (rodillo + guante de silicona +
atrapapelos de lavadora). IVA incluido, envío gratis.

### La diferenciación, y es honesta

El producto **no limpia mejor** que un rodillo de supermercado. Lleva recambios como
cualquier otro. Lo que cambia es **la tapa**:

- En el cajón no coge polvo, así que no hay que arrancar dos hojas antes de usarlo.
- Se puede llevar en el bolso o la guantera sin que se pegue a todo.
- Está listo cuando lo coges.

**El producto no limpia mejor: está disponible.** El 95 % del tiempo está guardado, no en
uso, y ahí es donde gana. Ese es el argumento y es suficiente.

### El competidor real

No es Amazon: es **no hacer nada**. La mayoría convive con el pelo y ha dejado de buscar
solución. El anuncio no debe convencer de que somos mejores, sino **volver a hacerles ver
el pelo**. Y la compra es por descubrimiento (un vídeo), no por búsqueda: en búsqueda de
producto se pierde siempre contra Amazon.

## 4. Economía

| | Rodillo | Kit |
|---|---|---|
| PVP (IVA incl.) | 34,99 € | 44,99 € |
| Base imponible | 28,92 € | 37,18 € |
| Coste desembarcado (VERIFICADO en CJ 28-ago) | 13,44 € (\$14,77) | 17,14 € |
| **Margen de contribución** | **15,18 €** | **19,53 €** |
| CPA break-even / objetivo | 15,18 € / 9,11 € | 19,53 € / 11,72 € |

> **El margen neto NO es del 60 %.** El bruto sí, pero tras restar el coste de captar
> cliente (8-14 € realistas en Meta/TikTok España), pasarela y devoluciones, el neto
> queda en **15-30 %**. Cualquier plan que asuma más que eso está mal planteado.

**Proveedor:** CJ Dropshipping, SKU `CJMY200580807GT`, vendedor PREMIUMGOODS (Zhejiang).
⚠️ **Envío desde China, 8-18 días naturales.** El «almacén en España» que figuraba aquí
hasta el 1-sep-2026 **no aplica a este SKU** — se verificó en la ficha real de CJ el
28-ago-2026 y el stock está en fábrica, no en España. Coste verificado: producto \$5,80
+ envío \$8,97 = **\$14,77** puesto en España. Evidencia en
`data/VERIFICACION-CJ-2026-08-28.md` del proyecto local.

---

## 5. Qué está hecho

### Tienda (5 páginas, HTML estático sin build)
- Portada de conversión en español de España
- Aviso legal · Política de privacidad (RGPD) · Términos y condiciones · Devoluciones
- Alojada en **GitHub Pages**. Rutas relativas, funciona en raíz y en subdirectorio.

### Datos (Supabase, proyecto `garcia-os`, región eu-west-3)
- `zeropelo_leads` — altas de correo. Consentimiento expreso obligatorio a nivel de RLS.
- `zeropelo_eventos` — analítica: `visita`, `clic_comprar`, `clic_kit`, `alta_email`.
- **Sin cookies, sin IP, sin user agent** → la tienda no necesita banner de cookies.
- Ambas **separadas de `public.leads`**, que pertenece al otro negocio del propietario.
- Verificado: la clave pública solo permite INSERT, no lee ningún correo.

### Material publicitario (en el proyecto local, `anuncios/`)
- 4 creatividades de anuncio · 4 escenas de contexto · 1 recorte con fondo transparente
- 2 vídeos de 5 s en 9:16 (demo de la franja limpia + UGC)
- Copy, 6 ganchos, 4 textos de anuncio y guion de vídeo en `anuncios/COPY_Y_GUIONES.md`

---

## 6. Decisiones que NO deben revertirse sin pensarlo

Estas cosas parecen omisiones y son deliberadas:

1. **No hay testimonios.** Los huecos están marcados como pendientes. Inventar reseñas
   está prohibido por la Directiva Ómnibus (RDL 24/2021 en España).
2. **No hay precio tachado ni descuento.** El mismo decreto exige que todo precio
   anterior sea el más bajo de los 30 días previos. Sin histórico, tacharlo es engañoso.
3. **No hay contador de urgencia ni «quedan X unidades».** Misma norma.
4. **No se quitaron marcas de agua a fotos del proveedor.** Se generó creatividad
   original. Quitar watermarks es infracción de copyright y Meta/TikTok lo rechazan.
5. **Las páginas legales no son decorativas.** Omitir los datos del titular es
   infracción sancionable por el artículo 38 de la LSSI-CE.

---

## 7. Trampas técnicas ya descubiertas

**No despliegues en Cloudflare Pages para público español.** Los rangos de Cloudflare
que sirven `*.pages.dev` (188.114.96.0/24 y 188.114.97.0/24) están **bloqueados desde
redes españolas**. Se comprobó: la tienda desplegada allí no se veía ni desde el
navegador del propio propietario, mientras GitHub Pages y otros rangos de Cloudflare sí
respondían. Usa **GitHub Pages**.

**Los vídeos de Higgsfield salen en H.265 (HEVC) con el índice al final.** Chrome no los
reproduce; QuickTime, Safari, TikTok, Instagram y Meta Ads sí. Para editar o incrustar
en web hay que convertirlos. Este Mac no tiene ffmpeg, pero sí `avconvert` nativo:
```bash
avconvert --source entrada.mp4 --preset Preset1920x1080 --output salida.mp4 --replace
```

**Para que el producto salga idéntico entre creatividades**, hay que pasar la imagen
original como *referencia* y pedir explícitamente «sin cambios de forma, color ni
proporciones». Sin eso, el generador cambia la forma del producto entre imágenes.

**Al editar HTML por índice de cadena, cuidado con `<script>` dentro de comentarios.**
Así se vació el `<body>` entero el 27/08/2026. Validar la estructura del documento
completo, no solo el trozo modificado.

---

## 8. Qué falta, y depende solo del propietario

| # | Paso | Por qué no puede hacerlo un asistente |
|---|---|---|
| 1 | Pedirse una muestra del producto | Requiere su tarjeta. Y sin producto real no hay vídeo real. |
| 2 | Crear cuenta Stripe y dos Payment Links | Requiere su identidad fiscal e IBAN. |
| 3 | Rellenar los datos de la SL en las 4 páginas legales | Son datos de su sociedad. Los huecos ya están en forma societaria. |
| 4 | Decidir quién paga las devoluciones | Decisión de negocio **con efecto legal**: si lo paga el cliente hay que avisarlo ANTES del pedido, o lo paga el vendedor por ley (art. 108.2 RDL 1/2007). |
| 5 | Borrar el aviso «Tienda en preparación» y publicar | Un `git push`. |

**Vehículo fiscal: SL española.** El propietario dispone de una sociedad limitada
registrada en España que actuará como paraguas de este y otros proyectos. Con su CIF se
abren pasarela de pago, cuenta bancaria y cuentas de proveedor, y figura como titular en
el aviso legal. Las páginas legales ya están en forma societaria (incluidos datos
registrales, exigibles a personas jurídicas por la Ley 34/2002).

Ventaja no menor: la responsabilidad queda limitada al capital social, lo que importa en
un negocio donde el vendedor es *importador* a efectos de la Directiva 85/374/CEE.

Queda por confirmar: poder de representación, que el objeto social cubra el comercio
electrónico, que la sociedad esté al corriente, y el epígrafe de IAE (normalmente el 665).
El detalle está en `FISCAL.md` del proyecto local, que **no se publica**.

**Cómo conectar el pago:** en `index.html`, al final, hay una constante `PAGOS` con dos
huecos vacíos. Pegando ahí los enlaces de Stripe, los botones funcionan solos.

---

## 9. Nunca metas aquí

Este repositorio es **público**. No debe contener jamás:
datos fiscales o personales, claves de Stripe o de cualquier pasarela, la clave de
servicio de Supabase, correos de clientes, ni credenciales de ningún tipo.

La clave pública de Supabase que aparece en `index.html` sí puede estar ahí: es
publicable por diseño y solo permite insertar, nunca leer.
