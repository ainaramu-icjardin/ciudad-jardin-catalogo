# 📚 CIFP Ciudad Jardín - Catálogo en Línea

Catálogo interactivo de programas formativos con filtros por nivel y familia profesional.

**Demo:** Archivo `index.html` listo para desplegar en cualquier servidor web estático.

---

## ✨ Características

✅ **Filtros avanzados** - Por nivel de formación y familia profesional
✅ **Datos en tiempo real** - Conectado a Supabase Cloud (160 registros)
✅ **Diseño Ciudad Jardín** - Colores y tipografía oficial de la escuela
✅ **Responsive** - Funciona en móvil, tablet y desktop
✅ **Carga rápida** - HTML autónomo, sin dependencias externas
✅ **Accesible** - Interfaz clara y fácil de usar

---

## 🚀 Despliegue Rápido

### Opción A: Netlify (Recomendado - sin código necesario)
1. Ir a https://app.netlify.com/drop
2. Arrastrar `index.html`
3. ¡Listo! 🎉

### Opción B: GitHub Pages
```bash
git init
git add index.html
git commit -m "Catálogo Ciudad Jardín"
git remote add origin https://github.com/TU_USUARIO/ciudad-jardin-catalogo.git
git push -u origin main
# Activar GitHub Pages en Settings
```

### Opción C: Vercel
```bash
npm install -g vercel
vercel --prod
```

### Opción D: Cloudflare Pages
```bash
npm install -g wrangler
wrangler pages deploy .
```

**Ver guía completa:** [HOSTING_GUIDE.md](HOSTING_GUIDE.md)

---

## 📁 Archivos del Proyecto

```
curso_agents/
├── index.html                    # 📄 Catálogo (archivo principal)
├── dev-server.js               # 🔧 Servidor para desarrollo local
├── HOSTING_GUIDE.md            # 📖 Guía de despliegue completa
├── DEPLOYMENT_SUMMARY.md       # ✅ Resumen de base de datos
├── export_data_inserts.sql     # 🗄️ Datos SQL de origen
└── supabase/migrations/        # 🔄 Migraciones Supabase
    └── 20260915201423_...sql
```

---

## 🎯 Contenido del Catálogo

**4 Niveles formativos:**
- Grado Medio
- Grado Superior
- Curso de Especialización
- Grado C

**4 Familias profesionales:**
- Administración y Gestión
- Comercio y Marketing
- Informática y Comunicaciones
- Servicios Socioculturales y a la Comunidad

**18 Programas** (ej: Gestión Administrativa, Desarrollo de Aplicaciones Web, etc.)

**134 Módulos** asociados a los programas

---

## 💻 Desarrollo Local

### Con Node.js:
```bash
node dev-server.js
# Abrir http://localhost:3000
```

### Con Python:
```bash
python3 -m http.server 3000
# Abrir http://localhost:3000
```

### Con VS Code:
Instalar extensión "Live Server", click derecho en `index.html` > "Open with Live Server"

---

## 🔗 Integración con Supabase

El catálogo consume datos de Supabase Cloud vía REST API:

**Proyecto:** `kyckwehxtyjggpsclxbc`
**URL:** https://kyckwehxtyjggpsclxbc.supabase.co

**Endpoints utilizados:**
- `/rest/v1/levels` - 4 registros
- `/rest/v1/families` - 4 registros
- `/rest/v1/programs` - 18 registros
- `/rest/v1/modules` - 134 registros

**Autenticación:** API key pública (anon key) - lectura solamente

---

## 🎨 Estilos y Personalización

El HTML usa la paleta de colores oficial de Ciudad Jardín:

| Color | Código | Uso |
|-------|--------|-----|
| Burgundy | `#7A1020` | Títulos, énfasis |
| Navy | `#003A70` | Headers, botones |
| Teal (Informática) | `#0F766E` | Familia profesional |
| Purple (Administración) | `#7E22CE` | Familia profesional |
| Orange (Comercio) | `#C2410C` | Familia profesional |
| Green (Transporte) | `#15803D` | Familia profesional |

Editar variables CSS en `index.html` (primeras líneas del `<style>`) para personalizar.

---

## ✅ Checklist Post-Despliegue

- [ ] La página carga sin errores
- [ ] Los filtros funcionan (selecciona nivel y familia)
- [ ] Se cargan los 18 programas
- [ ] Aparecen módulos asociados a cada programa
- [ ] El diseño es responsive en móvil
- [ ] Console (F12) no muestra errores

---

## 📊 Estadísticas

- **Registros totales:** 160
- **Tamaño del HTML:** ~20 KB (sin minificar)
- **Tiempo de carga:** < 1 segundo (con Supabase)
- **Navegadores soportados:** Todos los modernos (Chrome, Firefox, Safari, Edge)
- **Mobile:** Totalmente responsive

---

## 🔐 Seguridad

- ✅ API key anon solamente (lectura)
- ✅ Sin backend propio necesario
- ✅ CORS habilitado en Supabase
- ✅ Sin datos sensibles expuestos
- ✅ SSL/TLS en todos los proveedores

---

## 📖 Documentación Relacionada

- [HOSTING_GUIDE.md](HOSTING_GUIDE.md) - Instrucciones detalladas de despliegue
- [DEPLOYMENT_SUMMARY.md](DEPLOYMENT_SUMMARY.md) - Estado de la base de datos
- [Supabase Docs](https://supabase.com/docs)
- [GitHub Pages Docs](https://pages.github.com/)
- [Netlify Docs](https://docs.netlify.com/)

---

## 🤝 Soporte

**Problemas comunes:**

**P: Los datos no cargan**
R: Verificar conexión a internet, consola del navegador (F12), y que la API key sea correcta.

**P: El diseño no se ve bien**
R: Probablemente sea un problema de viewport. Verificar meta viewport en el HTML.

**P: Quiero agregar más programas**
R: Los datos se cargan dinámicamente de Supabase. Agregar registros en la BD y se mostrarán automáticamente.

---

## 📅 Información del Proyecto

- **Creado:** 15 de Septiembre de 2026
- **Base de datos:** Supabase Cloud (kyckwehxtyjggpsclxbc)
- **Tecnología:** HTML5 + CSS3 + JavaScript vanilla
- **Estado:** ✅ Producción
- **Última actualización:** 15 de Septiembre de 2026

---

**¿Preguntas? Revisar [HOSTING_GUIDE.md](HOSTING_GUIDE.md) para instrucciones de despliegue en detalle.**
