# Política de privacidad · GitHub Pages

Página estática en español, adaptable a celular y lista para desplegar con GitHub Actions. No requiere Node.js, npm, claves ni compilación. Conserva el texto del borrador, incluidos los campos entre corchetes. No incluye scripts, formularios, fuentes externas ni analítica.

## Publicar

1. Crea en GitHub un repositorio vacío llamado `privacidad-bot`. Puedes hacerlo público para usar GitHub Pages con GitHub Free.
2. Descomprime este ZIP. Abre una terminal dentro de la carpeta `privacidad-bot`, donde están `README.md`, `site` y `.github`.
3. Ejecuta lo siguiente, reemplazando `TU_USUARIO`:

```bash
git init -b main
git add .
git commit -m "Agregar política de privacidad y despliegue Pages"
git remote add origin https://github.com/TU_USUARIO/privacidad-bot.git
git push -u origin main
```

4. En el repositorio, entra en **Settings → Pages → Build and deployment → Source** y selecciona **GitHub Actions**.
5. En **Actions → Publicar política en GitHub Pages → Run workflow**, selecciona `main` y ejecútalo. Si el primer push falló porque aún no habías activado Pages, vuelve a ejecutar el workflow.
6. Espera que el job termine en verde. La URL aparecerá en el despliegue y en Settings → Pages. Normalmente será `https://TU_USUARIO.github.io/privacidad-bot/`.
7. Copia esa URL en el campo **URL de la política de privacidad** de Meta Developers.

Para subir por la interfaz web, incluye el contenido de la carpeta, no el ZIP. Asegúrate de que `.github/workflows/deploy-pages.yml` exista en esa ruta exacta; si el explorador omite carpetas ocultas, usa Git o crea el archivo desde GitHub. `site` y `.github` deben quedar en la raíz del repositorio, sin una carpeta `privacidad-bot` adicional.

## Editar

Edita `site/index.html` y reemplaza todas las apariciones de:

- `[NOMBRE DEL BOT]`
- `[CORREO DE CONTACTO]`
- `[NOMBRE DEL ABOGADO O ESTUDIO]`
- `[PROVEEDOR DE ALOJAMIENTO]`

Actualiza también la fecha visible y el atributo `datetime` al cambiar la política. Conservamos los campos pendientes por solicitud; completa los datos antes de usar la política como versión definitiva. La promesa de eliminación requiere que n8n, los temporales, registros y respaldos estén configurados de forma coherente. La página por sí sola no cambia el tratamiento del bot.

Cada push a `main` vuelve a publicar automáticamente. Si cambias el nombre de la rama, ajusta `branches` y la condición `if` en el workflow. No hacen falta PAT ni secretos manuales: usa el token automático de GitHub Actions y OIDC.

## Vista local

Abre `site/index.html` en tu navegador, o ejecuta:

```bash
python -m http.server 8080 --directory site
```

Visita `http://localhost:8080`.

## Archivos

- `site/index.html`: política completa, disponible sin JavaScript.
- `site/styles.css`: estilos responsive y de impresión.
- `site/.nojekyll`: sitio estático.
- `.github/workflows/deploy-pages.yml`: despliegue mediante acciones oficiales.

Solo se publica el contenido de `site`; README y workflow no forman parte del sitio desplegado. El despliegue real debe comprobarse en tu repositorio: este paquete no se ha conectado a una cuenta de GitHub.

Documentación: https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages
