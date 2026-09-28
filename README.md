# Sports & Lingo — web

Web pública de Sports & Lingo: familias, programas (digital y presencial), demo interactiva, paneles de familia y de niño, aula online. Trilingüe ES / CA / EN.

Es una web estática: no necesita build ni dependencias.

## Estructura

```
index.html      Página completa (todas las pantallas; navegación interna sin recargar)
support.js      Runtime que monta la página (no editar)
i18n.js         Diccionario de traducciones ES → CA / EN
assets/         Logos, favicon y personajes (webp/png optimizados)
netlify.toml    Configuración de despliegue en Netlify
```

## Probar en local

Hace falta un servidor (abrir el archivo con doble clic no carga los scripts):

```
npx serve .
# o
python3 -m http.server 8000
```

## Publicar

**Netlify**: New site → Import from GitHub → este repo. Sin comando de build; carpeta de publicación `.` (ya está en `netlify.toml`).

**Hostinger**: sube el contenido de la carpeta a `public_html/` (o conecta el repo desde hPanel → Git).

## Configuración pendiente

Al principio del bloque `<script data-dc-script>` de `index.html`:

- `INTRO_VIDEO_URL` — enlace *embed* del vídeo "Qué es Sports & Lingo" (p. ej. `https://www.youtube.com/embed/ID`). Vacío = marco de "vídeo pendiente".
- `STRIPE_LINKS.group8` / `STRIPE_LINKS.solo8` — Payment Links de Stripe para los packs de 8 sesiones (110 € grupo / 220 € particular). Vacíos = los botones llevan a Contacto.

## Traducciones

Los textos se escriben en español dentro de `index.html`. Para traducir uno nuevo, añade la misma frase exacta como clave en `i18n.js` en los bloques `ca` y `en`.

## Pendiente de desarrollo (fuera de esta web estática)

- Reservas: Cal.com (conectado al Google Calendar de cada profesor) + Stripe.
- Aula online integrada: Whereby embebido en la pantalla "aula", con grabación y transcripción → informes con IA para profesor, familia y equipo.
- Login real y datos de los paneles (hoy son datos de ejemplo).
