# ESTUDIA+ — instalación

Proyecto en HTML, CSS, Bootstrap 5, JavaScript modular y Firebase Authentication + Cloud Firestore.

1. Crea un proyecto en https://console.firebase.google.com/ y registra una aplicación **Web**. Copia la configuración que te proporciona Firebase en `firebase-config.js` (sustituye los valores REEMPLAZAR).
2. En Firebase Console > Authentication > Sign-in method, habilita **Anónimo**.
3. En Firestore Database crea la base de datos (elige una región adecuada). En **Reglas**, sustituye el contenido por `firestore.rules` y pulsa **Publicar**. No dejes las reglas de modo de prueba.
4. Sirve la carpeta desde un servidor local; no abras `index.html` con `file://`. Con VS Code utiliza Live Server, o desde esta carpeta ejecuta `python -m http.server 5500` y visita http://localhost:5500.
5. Para publicar, sube los archivos a Firebase Hosting o a un hosting HTTPS compatible. Si Firebase Auth solicita dominios autorizados, agrega el dominio donde publicaste la web en Authentication > Settings > Authorized domains.

**Importante:** La sesión es anónima y está vinculada a la instalación del navegador: si se borran los datos del sitio, se cambia de dispositivo o se pierde la sesión, el usuario puede perder acceso a sus registros. Para sincronizar entre dispositivos, agrega autenticación con Google/correo y vinculación de cuentas antes de usar en producción. No coloques claves privadas de servicio en el frontend. Los datos de estado de ánimo son personales; muestra una política de privacidad y solicita consentimiento antes de publicar para terceros.

**Alcance:** Se guardan tareas, prácticas y último estado de ánimo en Firestore; el progreso se calcula a partir de esos registros. El temporizador y la respiración son temporales y no guardan sesiones automáticamente. La interfaz es adaptable a móviles. No incluye notificaciones, PWA ni cuentas permanentes.
