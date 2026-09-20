# ESTUDIA+ — instalación

Sitio con HTML, CSS, Bootstrap 5, JavaScript y Firebase. Incluye siete secciones, registro con correo y contraseña, acceso Google, recuperación de contraseña y progreso individual en Firestore. No hay modo invitado.

1. Abre esta carpeta en Visual Studio Code y usa **Live Server** sobre `index.html` (por ejemplo, `http://127.0.0.1:5500`). No abras con `file://`.
2. En Firebase Console, proyecto **estudia-3bf91**, Authentication > Método de acceso: habilita **Google** y **Correo electrónico/contraseña**.
3. Authentication > Configuración > Dominios autorizados: autoriza el host de tu servidor local (`localhost` o `127.0.0.1` si Firebase permite agregarlo) y el dominio de producción. Si un dominio local no es admitido, usa uno autorizado o Firebase Hosting.
4. Firestore Database > Reglas: pega el contenido de `firestore.rules` y presiona **Publicar**. Estas reglas permiten solo datos propios y validan los registros que escribe la aplicación.
5. Recarga la web, crea una cuenta y agrega una tarea. Comprueba en Authentication > Usuarios y en Firestore > usuarios > UID > tareas.

La configuración web pública de Firebase está en `firebase-config.js`; nunca pongas claves privadas de servicio en el navegador. El estado de ánimo es información personal: prepara aviso de privacidad y medidas apropiadas si se usa con menores. La autenticación no requiere crear manualmente colecciones. El temporizador y la respiración no se guardan automáticamente.


## Diseño renovado
Se agregó ui.js (interacciones visuales, filtro de tareas, barra de avance y menú móvil), y se renovaron index.html y styles.css. Se conservan app.js, firebase-config.js y firestore.rules para mantener las cuentas y datos existentes. Para desplegar en Vercel, sube todos los archivos, incluido ui.js. Prueba Google, correo, tareas y progreso en el dominio publicado.

## Nueva pantalla de acceso
Se oculta la navegación mientras no hay sesión; registro e inicio de sesión tienen vistas, textos y transiciones diferenciados. `auth-ui.js` controla únicamente la presentación; `app.js` mantiene Firebase y el guardado de datos.


## Versión 3: experiencia renovada
- Inicio convertido en panel personal con contadores calculados de tareas y prácticas existentes.
- Secciones independientes con transición, barra inferior móvil y menú Más.
- Respiración guiada con animación opcional, respetando movimiento reducido.
- Autenticación y rutas de Firestore conservadas; no borres la base de datos ni cambies las reglas sin revisarlas.
- Archivos nuevos: experience.js. Publica todos los archivos juntos en Vercel.
- Comprueba el flujo de Google, tareas, prácticas, ánimo y cierre de sesión antes de sustituir el despliegue actual.


## Edición interactiva
Incluye `enhancements.js`: temas claro/oscuro, calendario de tareas existentes, logros basados en datos reales, modo de concentración, avatar y nombre personalizables. El perfil se guarda mediante merge en `usuarios/{uid}/datos/perfil`, sin sobrescribir el estado de ánimo. Los avatares son emojis; no se suben fotografías ni se requiere Firebase Storage. No elimina datos existentes ni cambia las rutas de Firestore. Las celebraciones se muestran al alcanzar un logro durante la sesión; no son un historial persistente. El temporizador sigue funcionando mientras la pestaña esté abierta. Publica todos los archivos de esta carpeta juntos.
