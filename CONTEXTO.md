# ZEROPELO — Contexto completo del proyecto

> **Si eres un asistente leyendo esto por primera vez:** este documento es el punto de
> entrada. Contiene de dónde viene el proyecto, qué se ha hecho, qué decisiones se
> tomaron y por qué, y qué queda pendiente. Lee entero antes de proponer nada.
>
> **Última actualización:** 2026-08-27

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

## 3. El producto y por qué se eligió

**Rodillo quitapelos reutilizable.** Sin adhesivo, sin recambios, sin pilas: el pelo se
acumula en una cámara interior que se abre y se vacía.

**Precios:** 24,99 € el rodillo · 34,99 € el kit (rodillo + guante de silicona +
atrapapelos de lavadora). IVA incluido, envío gratis.

### Por qué este y no otro

- **El dolor está confirmado como mainstream en España.** Medios generalistas
  publicaron en 2026 artículos sobre cómo quitar el pelo de mascota del sofá.
- **Mercado:** más de 16 millones de mascotas en España (9,3 M perros, 5,8 M gatos).
  El gasto en accesorios subió un 7,3 % en dos años; el canal online crece al 8,17 % anual.
- **Encaja en el patrón que convierte en TikTok Shop España:** 6-45 € con demostración
  clara en cámara. Este producto *es* su propia demostración.
- **Criterio decisivo, añadido durante la ejecución: «si falla, no pasa nada».**
  Al importar de China, el vendedor es *importador* a efectos de la Directiva
  85/374/CEE y responde como productor. Se descartaron productos cuyo fallo cause daño.

### Qué se descartó y por qué

| Producto | Motivo |
|---|---|
| Hamaca de ventana para gato | Sostiene un animal vivo en altura con ventosas. Riesgo de responsabilidad por producto inaceptable, pese a mejor valor percibido. |
| Protector de sofá antiarañazos | Saturado: ya lo distribuyen Leroy Merlin, Tiendanimal, ManoMano y SHEIN. |
| Fuente de agua / juguete láser | Batería o bomba: marcado CE, directiva RAEE, litio encarece el envío aéreo. |
| Comedero antivoracidad | Contacto alimentario: Reglamento (CE) 1935/2004. |

---

## 4. Economía

| | Rodillo | Kit |
|---|---|---|
| PVP (IVA incl.) | 24,99 € | 34,99 € |
| Base imponible | 20,65 € | 28,92 € |
| Coste desembarcado (estimado) | 5,80 € | 9,50 € |
| **Margen bruto** | **71,9 %** | **67,2 %** |
| Markup | x4,3 | x3,7 |

> **El margen neto NO es del 60 %.** El bruto sí, pero tras restar el coste de captar
> cliente (8-14 € realistas en Meta/TikTok España), pasarela y devoluciones, el neto
> queda en **15-30 %**. Cualquier plan que asuma más que eso está mal planteado.

**Proveedor:** CJ Dropshipping, **con almacén en España** → 3-7 días de entrega, frente
a 2-4 semanas desde China. Ese plazo es el argumento comercial principal de la tienda.
Los costes están marcados como ESTIMADO: CJ bloquea el acceso automatizado y no se
pudieron verificar. Detalle en `data/proveedor.json` del proyecto local.

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
| 3 | Rellenar los datos fiscales en las 4 páginas legales | Son sus datos. |
| 4 | Decidir quién paga las devoluciones | Decisión de negocio **con efecto legal**: si lo paga el cliente hay que avisarlo ANTES del pedido, o lo paga el vendedor por ley (art. 108.2 RDL 1/2007). |
| 5 | Borrar el aviso «Tienda en preparación» y publicar | Un `git push`. |

**Decisión de fondo abierta:** darse de alta como autónomo. Vender de forma habitual en
España lo exige.

**Cómo conectar el pago:** en `index.html`, al final, hay una constante `PAGOS` con dos
huecos vacíos. Pegando ahí los enlaces de Stripe, los botones funcionan solos.

---

## 9. Nunca metas aquí

Este repositorio es **público**. No debe contener jamás:
datos fiscales o personales, claves de Stripe o de cualquier pasarela, la clave de
servicio de Supabase, correos de clientes, ni credenciales de ningún tipo.

La clave pública de Supabase que aparece en `index.html` sí puede estar ahí: es
publicable por diseño y solo permite insertar, nunca leer.
