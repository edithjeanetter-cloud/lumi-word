# Lumi English — MVP para Google Sites

Este paquete contiene un MVP visual de Lumi English y el diseño original de Lumi. Está basado en la estructura pedagógica de `Teach Me`: objetivo, ruta, enseñanza, práctica guiada, feedback, aplicación y cierre; sesiones de 20–30 minutos; adaptación de dificultad; inglés cotidiano; vocabulario + conversación + pronunciación.

## Cómo ponerlo en Google Sites

1. Publica `index.html` y la carpeta `assets/` en un hosting HTTPS que permita carga de scripts y contenido en iframe.
2. En Google Sites: **Insertar → Insertar → Por URL** y pega la URL pública de la app, o usa **Insertar → Insertar código** para un bloque compatible.
3. Asegúrate de que el hosting permita ser embebido por Google Sites.

Google Sites permite insertar contenido web externo y código HTML/CSS/JavaScript, aunque algunos sitios pueden bloquear el embedding.

## Supabase

El MVP ya apunta al proyecto autorizado de Supabase y usa únicamente la clave pública `anon` en el cliente. No contiene una `service_role`/secret key.

Se crearon tablas nuevas, separadas de las tablas existentes de la aplicación anterior:
- `lumi_students`
- `lumi_lessons`
- `lumi_vocab`
- `lumi_progress`
- `lumi_attempts`
- `lumi_parent_consents`

Todas tienen RLS habilitado y las tablas de progreso/intentos restringen el acceso al usuario autenticado propietario.

## Tutoría IA y voz

El MVP incluye TTS del navegador y reconocimiento de voz del navegador para prototipar el flujo. La conversación mostrada es un modo demostración; no debe presentarse como IA generativa en producción.

Para una versión de pago real se debe conectar el chat y análisis de pronunciación a una Edge Function/backend seguro con las credenciales del proveedor de IA. Las claves secretas nunca deben ir al HTML ni al navegador.

## Menores

Antes de producción: implementar consentimiento parental verificable, controles familiares, minimización/retención de datos, política de privacidad y revisión legal de las obligaciones aplicables al servicio para menores.
