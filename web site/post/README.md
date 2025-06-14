# 📝 BszDox - Publicador de Posts Anónimos

Este módulo permite a los usuarios publicar de manera anónima un post en línea. Los posts se almacenan en **JSONBin** y se asocian al perfil del usuario a través de una API externa (**MockAPI**).

---

## 🚀 Características

- Crear y publicar posts con título y contenido.
- Generar automáticamente un enlace único para compartir.
- Copiar el enlace al portapapeles con un clic.
- Guardar el enlace publicado en el perfil del usuario autenticado (MockAPI).
- Recuperar un post si se accede directamente con `?id=XXXX`.

---
## 🛠️ Funcionalidad JavaScript 📤 Publicar Post
> Valida que el título y el contenido estén presentes.

Envía una petición POST a JSONBin.

Genera el enlace:
```html
https://bszdoxing.foroactivo.com/h22-visualizar?id=BIN_ID
```
Guarda el post en la API de usuarios de MockAPI.

## 📎 Copiar Link
Utiliza document.execCommand('copy') para copiar el enlace generado al portapapeles.

## 🔐 Guardar en perfil (MockAPI)
> Busca al usuario en localStorage.
> Localiza el usuario por nombre y contraseña en MockAPI.
> Agrega el nuevo post a su lista guardarpost.

## ♻️ Recuperar post por ID
Si se accede a la página con un parámetro ?id=..., el sistema recupera automáticamente el post correspondiente desde JSONBin y muestra el link generado.

## 🔗 APIs Usadas
#### JSONBin

Endpoint: https://api.jsonbin.io/v3/b
```js
Headers:
'X-Master-Key': '***************',
'X-Access-Key': '***************'
```
##### MockAPI
Métodos: `GET` , `PUT`
### ✍️ Autor
Desarrollado y Fundador :  `AvastrOficial`
