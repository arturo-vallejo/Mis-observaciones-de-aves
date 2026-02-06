# 🐦 Observaciones de iNaturalist — Sitio web con Baserow

Sitio web estático que muestra tus observaciones de iNaturalist con fotos y mapa interactivo, leyendo datos en vivo desde tu base de datos en Baserow.

## Configuración rápida

### 1. Crea un repositorio en GitHub
- Ve a [github.com/new](https://github.com/new)
- Nombre sugerido: `mis-observaciones`
- Hazlo **público** (necesario para GitHub Pages gratuito)
- Sube los archivos `index.html`, `config.js` y este `README.md`

### 2. Edita `config.js`
Abre el archivo y cambia estos dos valores:

```js
BASEROW_TOKEN: "tu-token-real-aqui",
BASEROW_TABLE_ID: "12345",
```

**¿Dónde encuentro estos datos?**
- **Token:** En Baserow → clic en tu avatar (abajo-izquierda) → Settings → API tokens → crea uno con permisos de lectura
- **Table ID:** Abre tu tabla en Baserow → mira la URL → `https://baserow.io/database/XXX/table/YYYY` → el ID es `YYYY`

### 3. Activa GitHub Pages
- Ve a tu repositorio → **Settings** → **Pages**
- Source: **Deploy from a branch**
- Branch: **main** / carpeta **/ (root)**
- Guarda y espera ~1 minuto

Tu sitio estará en: `https://tu-usuario.github.io/mis-observaciones/`

## Campos requeridos en Baserow

Tu tabla debe tener estos campos (los nombres deben coincidir exactamente):

| Campo | Tipo |
|---|---|
| ID_observacion | Number |
| URL_observacion | URL |
| Nombre_comun | Text |
| Nombre_cientifico | Text |
| Fecha | Date |
| Lugar | Text |
| Latitud | Number |
| Longitud | Number |
| Grado_calidad | Single select |
| Foto_URL | URL |
| Num_fotos | Number |
| Num_identificaciones | Number |

## ¿Cómo actualizar los datos?

Solo actualiza tu tabla en Baserow. El sitio lee los datos en vivo cada vez que alguien lo visita. No necesitas hacer nada más.

## Nota sobre seguridad

El token de Baserow queda visible en `config.js`. Para un sitio personal esto es aceptable si el token solo tiene permisos de **lectura**. Nunca uses un token con permisos de escritura en un sitio público.
