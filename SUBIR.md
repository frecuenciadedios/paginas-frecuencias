# Por qué solo funciona una URL, y cómo arreglarlo

Si `paginas-frecuencias.vercel.app` funciona pero `/manifestacion` y `/energia` dan error 404, es porque los archivos no están en la raíz del repositorio.

## Cómo verificarlo

Entrá a tu repositorio en GitHub. Tenés que ver los archivos **directamente**, así:

```
index.html
manifestacion.html
energia.html
portada-1.jpg
portada-2.jpg
portada-3.jpg
```

**Si en cambio ves una carpeta** (por ejemplo `paginas-frecuencias/` o `links/`) y los archivos están adentro, ese es el problema. Vercel sirve desde la raíz, no desde adentro de una carpeta.

## Cómo arreglarlo (la vía rápida)

1. En GitHub, entrá a tu repositorio.
2. Si hay una carpeta, entrá a ella.
3. Borrá todo: clic en cada archivo → ícono del tacho → Commit. O borrá la carpeta entera.
4. Volvé a la raíz del repositorio.
5. **Add file** → **Upload files**.
6. Arrastrá los archivos **sueltos**, sin carpeta. Importante: seleccioná los archivos uno por uno o todos juntos, pero NUNCA arrastres la carpeta que los contiene.
7. **Commit changes**.
8. Vercel se actualiza solo en un minuto.

## Comprobar que quedó bien

Abrí las tres direcciones:

```
https://TUPROYECTO.vercel.app/
https://TUPROYECTO.vercel.app/manifestacion
https://TUPROYECTO.vercel.app/energia
```

Las tres tienen que abrir. Si alguna da 404, los archivos siguen dentro de una carpeta.

## Nota sobre los nombres

Vercel toma el nombre del archivo como la ruta:

- `index.html` → la raíz (`/`)
- `manifestacion.html` → `/manifestacion`
- `energia.html` → `/energia`

No hace falta poner `.html` en la URL, Vercel lo resuelve solo.
