# Página de AgroCam

Esta es la página **https://agrocam-web.vercel.app**, desde donde la gente descarga la app AgroCam para Android.

Cada cambio que llega a la rama `main` se publica solo en Vercel, en uno o dos minutos.

## Qué hay aquí

| Archivo | Qué es |
|---|---|
| `index.html` | La página principal. El texto, el diseño (CSS) y el código (JavaScript) están en este mismo archivo. |
| `privacidad.html` | Aviso de privacidad. La app abre esta dirección. |
| `restablecer.html` | Página para crear una contraseña nueva. Ahí llega el enlace del correo de "olvidé mi contraseña". |
| `img/` | Fotos e ilustraciones, en formato WebP. |
| `AgroCam.apk` y `version.json` | La app y los datos de su versión. **No los toques**: los actualiza `publicar.sh` desde la computadora que tiene la llave de firma de la app. |

## Cómo hacer un cambio

### Opción fácil: desde GitHub

1. Abre el archivo (por ejemplo `index.html`) y da clic en el lápiz (**Edit**).
2. Haz tu cambio.
3. Da clic en **Commit changes…**, elige **Create a new branch** y ponle un nombre corto, como `cambio-textos`.
4. Abre el **Pull Request**. En unos minutos Vercel deja un comentario con un enlace de prueba (*Preview*). Revisa ahí que todo se vea bien, también en el celular.
5. Si todo está bien, da clic en **Merge**. La página real se actualiza en uno o dos minutos.

### Desde tu computadora

```sh
git clone https://github.com/SalvaPV/agrocam-web.git
cd agrocam-web
git switch -c mi-cambio
python3 -m http.server 8000      # abre http://localhost:8000 para ver la página
# ...haz tus cambios...
git add -A
git commit -m "Describe el cambio"
git push -u origin mi-cambio
```

Luego abre el Pull Request en GitHub y sigue los pasos 4 y 5.

## Reglas

- No subas cambios directo a `main`: usa una rama y un Pull Request para que alguien más lo revise.
- No borres ni cambies de nombre `version.json`, `AgroCam.apk`, `privacidad.html` ni `restablecer.html`: la app y los correos dependen de esas direcciones.
- Este repositorio es **público**: nunca pongas contraseñas ni llaves secretas. La llave `sb_publishable_…` que está en `restablecer.html` es pública a propósito.
- Las imágenes van en WebP y de preferencia de menos de 300 KB, para que la página cargue rápido con poca señal.
- Si cambias el precio, los días de prueba o lo que dice el aviso de privacidad, avisa al equipo: también hay que cambiarlo en la app.

El código de la app está en otro repositorio, privado: `SalvaPV/AgroCam`.
