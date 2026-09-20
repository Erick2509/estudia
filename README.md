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
