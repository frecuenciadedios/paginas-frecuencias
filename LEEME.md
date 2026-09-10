# Tus 3 páginas · Guía completa

Tres páginas con tu Pixel de Meta (ID 1639155350959159) ya adentro, el reproductor de Spotify embebido con los tracks, texto en español y portugués, y responsive probado desde 320px hasta desktop.

---

## PARTE 1 · Completar antes de subir

### 1.1 Las portadas

Descargá la portada de cada playlist desde Spotify (abrí la playlist, clic derecho sobre la imagen, Guardar imagen) y ponelas en la misma carpeta con estos nombres exactos:

- `portada-1.jpg` → Frecuencia de Dios 963 Hz
- `portada-2.jpg` → Manifestación
- `portada-3.jpg` → Atraer buenas energías

Cuadradas, mínimo 600x600. Las que vienen ahora son de relleno.

### 1.2 El ID de la playlist de Manifestación

Es lo único que falta. En `manifestacion.html` aparece dos veces el texto `PEGAR_ID_PLAYLIST_2`. Reemplazá las dos por el ID real.

Para sacarlo: abrí la playlist en Spotify → Compartir → Copiar enlace. Te queda algo así:

```
https://open.spotify.com/playlist/4aB7xY9zK2mNp3Q?si=abc123
```

El ID es lo que va entre `/playlist/` y el `?`. En el ejemplo: `4aB7xY9zK2mNp3Q`

Las otras dos páginas ya tienen su ID puesto.

### 1.3 Google Analytics (opcional pero recomendado)

Esto te devuelve las estadísticas que perdés al no usar Feature.fm: cuántos entraron, de qué país, cuántos hicieron clic.

1. Entrá a analytics.google.com y creá una propiedad gratis.
2. Te va a dar un ID que empieza con `G-`.
3. En los tres archivos, buscá `G-XXXXXXXXXX` (aparece dos veces en cada uno) y reemplazalo por tu ID.

Si no querés usarlo, dejalo como está: no rompe nada, simplemente no mide.

---

## PARTE 2 · Subir a Vercel

### Opción A · Sin GitHub (la más simple)

1. Entrá a **vercel.com** y creá cuenta gratis (con email, Google o GitHub).
2. Poné todos los archivos (los 3 HTML y las 3 portadas) dentro de una carpeta, por ejemplo `paginas`.
3. En Vercel, botón **Add New** → **Project**.
4. Buscá la opción de deploy sin repositorio: en la pantalla de importar suele haber un enlace que dice algo como "Deploy without Git" o podés arrastrar la carpeta directamente.
5. Arrastrá la carpeta completa.
6. Deploy.

### Opción B · Con GitHub (recomendada si vas a hacer cambios seguido)

1. Creá cuenta en **github.com** (gratis).
2. Botón **New repository**. Ponele un nombre, por ejemplo `paginas-frecuencias`. Dejalo público o privado, da igual.
3. En el repositorio nuevo, botón **uploading an existing file**.
4. Arrastrá los 3 HTML y las 3 portadas. **Commit changes**.
5. Entrá a vercel.com → **Add New** → **Project** → conectá tu GitHub → elegí ese repositorio → **Deploy**.

Con esta opción, cada vez que cambies algo en GitHub, Vercel actualiza solo.

### Después del deploy

Vercel te da una dirección tipo `paginas-frecuencias.vercel.app`. Tus tres links quedan:

```
https://TUPROYECTO.vercel.app/                 → Frecuencia de Dios
https://TUPROYECTO.vercel.app/manifestacion    → Manifestación
https://TUPROYECTO.vercel.app/energia          → Atraer buenas energías
```

Esos son los que pegás en cada anuncio de Meta.

---

## PARTE 3 · Verificar que el Pixel mide

1. En el Administrador de eventos de Meta, entrá a tu Pixel → pestaña **Probar eventos**.
2. Pegá una de tus URLs de Vercel en el campo que pide la URL del sitio y abrila desde ahí.
3. Apenas carga la página tenés que ver un evento **PageView**.
4. Hacé clic en el botón verde de Spotify.
5. Tiene que aparecer un evento **Lead**.

Si ves los dos, está todo funcionando. Repetí con los otros dos links.

**Importante:** hacelo sin bloqueador de anuncios. Si usás uno, probá en ventana de incógnito con las extensiones desactivadas, o desde el celular.

---

## PARTE 4 · La campaña en Meta

Como ahora el evento es un **Lead** propio, la conversión personalizada que habías creado con la regla `api.ffm.to/sl/e/c/` **ya no sirve**. Podés borrarla.

En su lugar, al configurar el conjunto de anuncios:

- **Evento de conversión:** elegí **Lead** (el evento estándar)

Nada más. No hace falta crear conversiones personalizadas.

### Si querés medir cada playlist por separado

Creá tres conversiones personalizadas con estas reglas:

| Nombre | Regla: la URL contiene |
|---|---|
| Clic · Fe | `/` con evento Lead (o usá el content_name) |
| Clic · Manifestación | `manifestacion` |
| Clic · Energía | `energia` |

Para **optimizar** la campaña usá siempre el evento **Lead** general: junta más datos y el algoritmo aprende más rápido. Las específicas son solo para mirar el detalle en los informes.

---

## PARTE 5 · Tu propio dominio (opcional)

Un dominio propio da más confianza que un `.vercel.app` y cuesta unos 12 dólares al año.

1. Comprá el dominio (Namecheap, GoDaddy, o el mismo Vercel).
2. En Vercel: tu proyecto → **Settings** → **Domains** → agregá el dominio.
3. Vercel te dice qué registros DNS configurar donde compraste el dominio.

Los links quedan tipo `frecuenciadedios.com/manifestacion`.

No es necesario para arrancar.

---

## Agregar más páginas después

Copiá cualquiera de los tres archivos, renombralo (por ejemplo `dormir.html`) y cambiá:

- El `<title>` y las meta descripciones
- El nombre de la portada (`src="portada-4.jpg"`)
- El `<h1>` y los dos párrafos (español y portugués)
- El ID de la playlist en el iframe y en el enlace del botón
- El `content_name` del script al final

Subilo a Vercel y ya tenés `tuproyecto.vercel.app/dormir`. Sin límite y sin pagar nada.

Sirve para Vida Sana y para cualquier otro artista.
