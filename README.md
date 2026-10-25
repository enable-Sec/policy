# Política de privacidad de Enable Sec.

## Actualizar GitHub Pages

El archivo `index.html` es autónomo: incluye los estilos y no requiere JavaScript, compilación ni dependencias.

1. Copia `index.html` a la raíz de tu repositorio `enable-Sec/policy`, reemplazando la política anterior.
2. Reemplaza el workflow anterior por `.github/workflows/deploy-pages.yml` incluido aquí. Mantén un único workflow de despliegue de Pages.
3. En Settings → Pages, elige GitHub Actions como origen.
4. Haz commit en `main`. El workflow crea `_site`, copia solo el HTML y publica esa carpeta. No requiere que exista `site`.
5. Comprueba el despliegue en Actions y abre https://enable-sec.github.io/policy/ .

Sube los archivos extraídos, no el ZIP ni una carpeta adicional. El workflow debe estar exactamente en `.github/workflows/deploy-pages.yml` y el HTML en `index.html`.

## Alcance de esta versión

Redactada a partir del funcionamiento declarado: recibir audio por WhatsApp, resumirlo con IA y enviar el texto al abogado o persona natural previamente identificada, sin almacenamiento propio posterior. Se mantiene Enable Sec. y contacto@enablesec.com según la información proporcionada. No se ha confirmado que Enable Sec. sea la razón social: antes de la versión definitiva, completa la identificación legal real de la empresa en la sección 1 (razón social, RUT y domicilio/contacto que corresponda).

La página no implementa los controles del bot. La afirmación de no almacenamiento exige que audios, textos, números e identificadores tampoco persistan en ejecuciones de n8n, errores, temporales, colas persistentes, logs, respaldos ni telemetría. Debe cumplirse también en ejecuciones fallidas. No hemos auditado la VM ni el flujo.

La API de xAI tiene condiciones propias de retención; no se asume ZDR activo. Verifica la modalidad y los endpoints de audio/texto que realmente utilices. Si usas Groq en vez de Grok o un proveedor adicional de transcripción, actualiza la sección 6 antes de publicar.

El destinatario debe identificarse en el bot antes del procesamiento. La política no da autorización para remitir consultas a personas indeterminadas. Implementa el aviso y la autorización descritos antes de solicitar el audio. El correo de privacidad y la copia recibida por el destinatario tienen un ciclo distinto al procesamiento temporal del bot.

## Aviso sugerido para el bot (adaptar al flujo)

Soy el asistente automatizado de Enable Sec. Usaré IA para resumir tu audio y enviar el texto a [NOMBRE DEL DESTINATARIO]. Enable Sec. no conserva el audio ni el resumen después de procesar el envío; WhatsApp, el proveedor de IA y el destinatario pueden conservar información según lo explicado en nuestra política: https://enable-sec.github.io/policy/ . ¿Autorizas este procesamiento y envío? Responde Acepto para continuar.

No envíes esta plantilla sin sustituir el destinatario. Este aviso no se muestra en la página pública.

## Revisión

Es un borrador ajustado al funcionamiento declarado, no una certificación legal ni una auditoría técnica. El despliegue en GitHub no se ejecutó desde esta conversación. No se agregaron herramientas analíticas, formularios ni almacenamiento en el navegador. GitHub Pages puede tratar registros técnicos propios al servir la página.

Fuentes consultadas el 24 de octubre de 2026:
- https://docs.x.ai/developers/faq/security
- https://www.bcn.cl/leychile/navegar?idNorma=141599&idVersion=2012-02-17

## Revisión

Siete secciones. Aviso y autorización redactados como comportamiento efectivo del bot: deben implementarse antes de publicar. Eliminación propia diferenciada de proveedores y destinatarios. Identificación legal de Enable Sec. pendiente, sin cambios en la sección 1.
