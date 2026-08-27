# ZEROPELO

Tienda de producto único: rodillo quitapelos reutilizable para mascotas.
Mercado España. HTML estático, sin build.

**En vivo:** https://alexghost1.github.io/zeropelo/

---

## 📖 Empieza por aquí

**[CONTEXTO.md](CONTEXTO.md)** — de dónde viene el proyecto, qué está hecho, qué
decisiones se tomaron y por qué, y qué queda pendiente.

Si eres un asistente al que le acaban de dar este repositorio: lee ese archivo entero
antes de proponer cambios. Contiene decisiones deliberadas que parecen omisiones.

Enlace directo para leerlo sin clonar:
`https://raw.githubusercontent.com/alexghost1/zeropelo/main/CONTEXTO.md`

---

## Estructura

```
index.html          Tienda
assets/styles.css   Estilos
legal/              Aviso legal · Privacidad · Términos · Devoluciones
public/images/      Imágenes del producto
CONTEXTO.md         Contexto completo del proyecto
```

## Publicar cambios

```bash
git add -A && git commit -m "..." && git push
```
GitHub Pages se actualiza solo en un par de minutos.

> ⚠️ **No despliegues en Cloudflare Pages.** Los rangos que sirven `*.pages.dev` están
> bloqueados desde redes españolas. Ver CONTEXTO.md, sección 7.
