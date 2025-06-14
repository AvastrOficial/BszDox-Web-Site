# 📄 BszDox - Visualizador de Post por ID

Este archivo JavaScript permite cargar y mostrar un **post anónimo** desde una API externa (JSONBin), utilizando un parámetro `id` pasado por la URL.

Ejemplo de URL funcional:
```html
https://tusitio.com/ver.html?id=xxxxxxxx
```

---

## 🚀 Funcionalidad principal

El script realiza las siguientes tareas:

1. **Lee el parámetro `id`** desde la URL.
2. **Obtiene los datos del post** (título, texto, autor) desde la API `https://api.jsonbin.io/v3/b/{id}`.
3. **Muestra el contenido en el HTML** usando los elementos con IDs: `post-title`, `post-text`, `post-author`.
4. **Convierte automáticamente cualquier URL** dentro del texto en enlaces clicables con estilo destacado.
5. **Permite compartir el post** copiando el enlace actual al portapapeles.

---

## 🔗 Conversión de URLs

Cualquier URL detectada en el texto del post será transformada en un enlace HTML que se abrirá en una nueva pestaña.  
Esto se hace usando la función `linkify()` que aplica esta expresión regular:

```js
/(https?:\/\/[^\s]+)/g
```
## 🛡️ Seguridad
Los enlaces se abren con target="_blank" y rel="noopener noreferrer" para evitar riesgos de seguridad (como ataques de tipo window.opener).

Si el id no está presente o la petición falla, se muestra un error amigable al usuario.
