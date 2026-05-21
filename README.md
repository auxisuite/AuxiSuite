# Auxi Suite — auxisuite.app

Sitio web estático para la suite de apps de productividad clínica para profesionales de la salud.

## Estructura de archivos

```
AUXI SUITE/
├── index.html          # Homepage principal
├── auxi-medical.html   # Página de Auxi Medical
├── auxi-flow.html      # Página de Auxi Flow
├── calculadoc.html     # Página de Calculadoc
├── support.html        # Soporte y contacto
├── privacy.html        # Política de privacidad
├── terms.html          # Términos de servicio
├── style.css           # Estilos globales
├── main.js             # JavaScript (nav, animaciones)
├── README.md           # Este archivo
└── logos_images/
    ├── auxi_suite_logo.png
    ├── auxi_logo.png
    ├── flow_logo.png
    ├── calculadoc_logo.png
    ├── auxi_meds_logo.png
    ├── auxi_protocols_logo.png
    ├── playstore_banner.jpg
    └── playstore_banner.png
```

---

## Antes de publicar — cosas que actualizar

1. **Links de Google Play**: Busca todos los `href="#"` en los botones de descarga y reemplázalos con los URLs reales de cada app en Google Play.
2. **Correo de soporte**: Si cambias de `support@auxisuite.app`, actualiza todos los archivos HTML y el formulario de soporte.
3. **Año del copyright**: El footer dice "© 2026". Actualiza anualmente.

---

## Opción 1: Deploy en GitHub Pages (recomendado — 100% gratis)

### Paso 1: Crear repositorio en GitHub
1. Ve a [github.com](https://github.com) y crea una cuenta si no tienes.
2. Crea un nuevo repositorio público: `auxisuite-web` (o el nombre que prefieras).
3. No inicialices con README (ya tenemos uno).

### Paso 2: Subir los archivos
```bash
# Desde la carpeta AUXI SUITE en tu terminal:
git init
git add .
git commit -m "Initial site commit"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/auxisuite-web.git
git push -u origin main
```

### Paso 3: Activar GitHub Pages
1. Ve a tu repositorio en GitHub.
2. Clic en **Settings** → **Pages** (menú izquierdo).
3. En "Source", selecciona **Deploy from a branch**.
4. Selecciona **main** branch y carpeta **/ (root)**.
5. Clic en **Save**.
6. En ~2 minutos el sitio estará en `https://tu_usuario.github.io/auxisuite-web/`.

### Paso 4: Conectar el dominio auxisuite.app
1. Crea un archivo llamado `CNAME` (sin extensión) en la raíz del proyecto con este contenido:
   ```
   auxisuite.app
   ```
2. Haz commit y push del archivo CNAME.
3. En tu proveedor de dominio (donde compraste auxisuite.app), configura los DNS:
   - **Tipo A** — apunta `@` a estas IPs de GitHub:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - **CNAME** — apunta `www` a `tu_usuario.github.io`
4. En GitHub Pages settings, escribe `auxisuite.app` en el campo "Custom domain".
5. Activa **Enforce HTTPS** (espera unos minutos para que genere el certificado SSL).

Los cambios de DNS pueden tardar entre 1 y 48 horas en propagarse.

---

## Opción 2: Deploy en Vercel (más rápido, mejor CDN)

### Paso 1: Crear cuenta y conectar GitHub
1. Ve a [vercel.com](https://vercel.com) y crea cuenta con tu GitHub.
2. Clic en **Add New → Project**.
3. Importa tu repositorio `auxisuite-web`.
4. Vercel detecta automáticamente que es un sitio estático.
5. Clic en **Deploy** — en ~30 segundos estará live.

### Paso 2: Conectar el dominio
1. En Vercel, ve a tu proyecto → **Settings** → **Domains**.
2. Agrega `auxisuite.app`.
3. Vercel te dará instrucciones específicas de DNS (generalmente un registro A o CNAME).
4. Configura esos registros en tu proveedor de dominio.

---

## Opción 3: Deploy en Netlify

1. Ve a [netlify.com](https://netlify.com) y crea cuenta.
2. Arrastra y suelta la carpeta entera del sitio en el dashboard de Netlify (modo drag & drop, sin necesidad de Git).
3. El sitio se publica instantáneamente con un URL de Netlify.
4. Para el dominio: **Site settings → Domain management → Add custom domain**.

---

## Hacer actualizaciones (después del primer deploy)

### Con GitHub Pages o Vercel (via Git):
```bash
# Edita los archivos que necesites, luego:
git add .
git commit -m "Descripción del cambio"
git push
```
El sitio se actualiza automáticamente en ~1-2 minutos.

### Con Netlify (drag & drop):
Simplemente arrastra la carpeta actualizada de nuevo al dashboard.

---

## Imágenes que podrían añadirse más adelante

| Imagen | Tamaño recomendado | Formato | Uso |
|--------|-------------------|---------|-----|
| Screenshots de Auxi Medical | 1080×1920 px | PNG/WebP | Sección de screenshots en la página de la app |
| Screenshots de Auxi Flow | 1080×1920 px | PNG/WebP | Sección de screenshots |
| Screenshots de Calculadoc | 1080×1920 px | PNG/WebP | Sección de screenshots |
| Mockup en teléfono | 800×1200 px | PNG | Sección hero en index.html |
| Foto del equipo (opcional) | 1200×800 px | JPG/WebP | Sección "Acerca de" futura |
| favicon.ico | 32×32 px | ICO/PNG | Ícono del navegador |

Para agregar screenshots, crea un folder `screenshots/` y referencia las imágenes en el HTML donde dice `<!-- screenshots section -->` (o agrega la sección nueva).

---

## SEO básico ya incluido

- Meta description en cada página
- Open Graph tags (para compartir en redes sociales)
- Titles descriptivos por página
- Estructura semántica HTML5 (h1, h2, section, nav, footer, main)
- Responsive (mobile-first)
- Favicons referenciados

Para mejorar el SEO más adelante, considera agregar:
- `sitemap.xml` con todas las páginas
- `robots.txt`
- Schema.org markup (JSON-LD) para MobileApplication
