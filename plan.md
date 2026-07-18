# Living73 15D - Welcome Book

## Contexto del Proyecto

**¿Qué es?** Welcome Book digital para un Airbnb llamado "Living73 15D" ubicado en Panamá. Es una guía para huéspedes con información de contacto, instrucciones de uso de electrodomésticos, lugares de interés y manuales descargables.

**¿Por qué existe?** Para que el huésped al escanear un QR pueda acceder a toda la información del alojamiento desde su celular.

**Referencia de diseño:** [cece.fi](https://www.cece.fi/) - Se analizó su estructura, tipografía, responsive y paleta de colores.

---

## Tecnologías

| Tecnología | Uso |
|------------|-----|
| HTML5 | Estructura (archivo único `index.html`) |
| CSS3 | Estilos embebidos en `<style>` (sin framework CSS externo) |
| Google Fonts | Inter (sans-serif) + Merriweather (serif) |
| JavaScript vanilla | Menú móvil, smooth scroll, header sticky |
| GitHub Pages | Hosting gratuito |
| Google My Maps | Mapa de lugares de interés embebido |

**NO se usa:** Tailwind, Bootstrap, ni ningún framework CSS o JS.

---

## Estructura de Directorios

```
WelcomeBook-html/
├── index.html              ← Archivo principal (autocontenido)
├── plan.md                 ← Este archivo
├── img/                    ← Imágenes (vacía por ahora)
├── pdf/                    ← PDFs locales (vacío, se usan links externos)
└── videos/
    ├── video_header.mp4    ← Video del hero
    ├── lavadora.mp4        ← Video de lavadora
    ├── aire_acond.mp4      ← Video de aire acondicionado
    └── aspiradora.mp4      ← Video de aspiradora
```

---

## Paleta de Colores

```css
--bg-primary: #f9f9f8;      /* Fondo cálido */
--bg-white: #ffffff;         /* Tarjetas */
--text-primary: #1c1917;     /* Texto principal */
--text-secondary: #57534d;   /* Texto secundario */
--accent: #292524;           /* Acentos oscuros */
--accent-light: #e7e5e4;     /* Fondos claros */
--border: #e7e5e4;           /* Bordes */
```

---

## Tipografía

- **Títulos:** Merriweather (serif) - `--font-serif`
- **Cuerpo:** Inter (sans-serif) - `--font-sans`
- Pesos: 300, 400, 500, 600, 700

---

## Secciones del HTML (en orden)

### 1. Header (fijo)
- Logo: "Living73 15D"
- Navegación: Contactos | Cómo Usar | Lugares | Descargas
- Menú hamburguesa en móvil

### 2. Hero
- Video de fondo: `videos/video_header.mp4` (autoplay, muted, loop)
- Título: "Bienvenidos a Living73 15D"
- Subtítulo: "Tu hogar lejos de casa..."

### 3. Contactos de Emergencia
Tarjetas con iconos SVG:
- **Bomberos:** 512-6148 / 512-6400 / 103
- **Policía Nacional:** 511-7000 / 104
- **Emergencias 911:** 911
- **Atención Ciudadana:** 311
- **Ambulancia Privada:** 374-0000 (7am-11pm) / 6259-8406 (11pm-7am)
- **Tu Anfitrión:** WhatsApp (pendiente número real)

### 4. Cómo Usar
Videos locales + textos explicativos:
1. **Aire Acondicionado** - `videos/aire_acond.mp4` (texto sobre pantalla LED y temperatura)
2. **Secadora** - `videos/secadora.mp4` (pendiente de subir)
3. **Plancha** - `videos/plancha.mp4` (pendiente de subir)
4. **Lavadora** - `videos/lavadora.mp4` (comienza en segundo 2, texto sobre uso en baño)
5. **Aspiradora** - `videos/aspiradora.mp4` (texto sobre closet de lavado, velocidad MID)

### 5. Lugares de Interés
- Texto descriptivo de la zona
- Mapa embebido de Google My Maps
- URL: `https://www.google.com/maps/d/u/0/embed?mid=1iYpAGl-rtoYjVcmq5AgWTXeOHDK4WhY&ehbc=2E312F&noprof=1`

### 6. Descargas
- **Manual de la Lavadora** → Scribd: `https://www.scribd.com/document/788896690/Dc68-04269h-02-Ib-U-pjt-Combo-md-Simpleux-Mes`
- **Manual de la Aspiradora** → `https://share.google/HatVjAZnXR4O1R2LD`
- **Reglas de la Casa** → `pdf/reglas-casa.pdf` (pendiente de crear)

### 7. Footer
- Mensaje: "¿Necesitas algo más?" + WhatsApp del anfitrión

---

## Responsive

- **Mobile-first** con breakpoint `sm:` (768px)
- En móvil: menú hamburguesa, columnas apiladas
- Videos: `aspect-ratio: 16/9`
- Mapa: 480px desktop → 350px móvil

---

## GitHub

- **Repositorio:** `https://github.com/rdrsando/living73-15d.git`
- **GitHub Pages:** `https://rdrsando.github.io/living73-15d/`
- **Rama:** `master`

---

## Pendientes

### Contenido
- [ ] Agregar número real de WhatsApp del anfitrión
- [ ] Subir video de secadora (`videos/secadora.mp4`)
- [ ] Subir video de plancha (`videos/plancha.mp4`)
- [ ] Crear PDF de "Reglas de la Casa" y subirlo a `pdf/` o enlazar externamente
- [ ] Agregar imágenes a `img/` si se necesitan

### Funcionalidad
- [ ] **Toggle ES/EN** - Traducción completa de todos los textos. Usar JavaScript con `localStorage` para persistir idioma. El usuario pidió implementarlo cuando todo el contenido esté listo.

### Diseño
- [ ] Verificar que todos los videos funcionen correctamente en el navegador
- [ ] Probar responsive en diferentes dispositivos
- [ ] Generar código QR con goqr.me o qr-code-generator.com

### Notas del usuario
- El usuario no sabe usar ffmpeg; para convertir videos usar herramientas online como cloudconvert.com o freeconvert.com
- Los PDFs se enlazan desde Scribd/Google en vez de subirlos localmente
- El mapa de Google My Maps requiere que sea público en la configuración de My Maps

---

## Instrucciones para otro agente

1. El HTML es un archivo único autocontenido (`index.html`) con CSS y JS inline
2. No hay build system, no hay dependencias npm, no hay framework
3. Para ver cambios: editar `index.html`, hacer push a GitHub, esperar ~1 minuto
4. Los videos se referencian como `videos/nombre.mp4`
5. Los enlaces externos usan `target="_blank" rel="noopener noreferrer"`
6. El archivo `plan.md` NO debe eliminarse, es la documentación del proyecto
