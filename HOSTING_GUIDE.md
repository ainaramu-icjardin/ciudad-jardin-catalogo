# 🚀 Guía de Despliegue - Catálogo Ciudad Jardín

El archivo `index.html` es autónomo y puede desplegarse en cualquier proveedor de alojamiento estático.

---

## 📋 Opción 1: GitHub Pages (Recomendado)

### Paso 1: Crear repositorio en GitHub
1. Ir a https://github.com/new
2. Nombre: `ciudad-jardin-catalogo`
3. Descripción: "Catálogo de programas formativos - CIFP Ciudad Jardín LHII"
4. Hacer público
5. Crear el repositorio

### Paso 2: Subir el archivo
```bash
# Clonar el repo
git clone https://github.com/TU_USUARIO/ciudad-jardin-catalogo.git
cd ciudad-jardin-catalogo

# Copiar el archivo
cp /Users/ainara/Proyectos/curso_agents/index.html .

# Subir a GitHub
git add index.html
git commit -m "Initial commit: Ciudad Jardín catalog"
git push origin main
```

### Paso 3: Activar GitHub Pages
1. En el repositorio, ir a **Settings** > **Pages**
2. En "Build and deployment":
   - Source: `Deploy from a branch`
   - Branch: `main` / `/root`
3. Guardar
4. La página estará en: **https://TU_USUARIO.github.io/ciudad-jardin-catalogo**

---

## 📋 Opción 2: Netlify (Más simple, sin GitHub requerido)

### Paso 1: Crear cuenta en Netlify
1. Ir a https://app.netlify.com
2. Registrarse con GitHub, Google o correo

### Paso 2: Desplegar el archivo
**Opción A - Arrastrar y soltar (más rápido):**
1. Abrir https://app.netlify.com/drop
2. Arrastrar `index.html` a la zona de drop
3. ¡Listo! Se generará una URL única

**Opción B - Via CLI:**
```bash
# Instalar Netlify CLI
npm install -g netlify-cli

# Desplegar
cd /Users/ainara/Proyectos/curso_agents
netlify deploy --prod --dir=.

# Seguir las instrucciones interactivas
```

### URL resultante:
`https://[random-nombre].netlify.app`

**Para un dominio personalizado:**
1. En Netlify, ir a **Site settings** > **Domain management**
2. Agregar dominio personalizado (ej: `catalogo.ciudad-jardin.es`)

---

## 📋 Opción 3: Vercel (Similar a Netlify)

### Paso 1: Crear cuenta en Vercel
1. Ir a https://vercel.com
2. Registrarse con GitHub, GitLab, Bitbucket o email

### Paso 2: Desplegar
```bash
# Instalar Vercel CLI
npm install -g vercel

# Desplegar
cd /Users/ainara/Proyectos/curso_agents
vercel --prod
```

O simplemente ir a https://vercel.com/new y conectar un repositorio de GitHub.

### URL resultante:
`https://[nombre-proyecto].vercel.app`

---

## 📋 Opción 4: Cloudflare Pages (Muy rápido)

### Paso 1: Crear cuenta en Cloudflare
1. Ir a https://dash.cloudflare.com
2. Registrarse

### Paso 2: Conectar GitHub o desplegar vía Wrangler
```bash
# Instalar Wrangler
npm install -g wrangler

# Desplegar
cd /Users/ainara/Proyectos/curso_agents
wrangler pages deploy .
```

O conectar el repositorio de GitHub directamente en el panel de Cloudflare.

### URL resultante:
`https://[nombre-proyecto].pages.dev`

---

## 🔑 Configuración del API Key de Supabase

El `index.html` ya contiene la API key pública (anon key) de Supabase:

```javascript
const SUPABASE_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imt5Y2t3ZWh4dHlqZ2dwc2NseGJjIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MTUxNDc2NzksImV4cCI6MTczMDgzNzY3OX0.s5m8ey7Vax34Auj5S2YpqQfmUiqPzYnNsRjJK7h7P-8';
```

**Notas de seguridad:**
- Esta es la anon key de Supabase (pública y segura de exponer)
- No incluye la service_role key (privada)
- El acceso solo es de lectura para la API REST
- Se puede cambiar si es necesario desde el panel de Supabase

---

## ✅ Verificación Post-Despliegue

Después de desplegar, verifica:

1. **La página carga sin errores**: Abre la URL en el navegador
2. **Los filtros funcionan**: Selecciona un nivel y familia
3. **Se cargan los datos**: Deberías ver 18 programas
4. **Consola sin errores**: Abre DevTools (F12) > Console

---

## 🎯 Comparativa de Proveedores

| Proveedor | Facilidad | Dominio Gratis | Performance | Características |
|-----------|-----------|---|---|---|
| **GitHub Pages** | ⭐⭐⭐ | sí (github.io) | ⭐⭐⭐ | Versionado Git, CDN |
| **Netlify** | ⭐⭐⭐⭐ | sí (netlify.app) | ⭐⭐⭐⭐ | Drag & drop, CLI simple |
| **Vercel** | ⭐⭐⭐⭐ | sí (vercel.app) | ⭐⭐⭐⭐ | Optimizado para SPA |
| **Cloudflare Pages** | ⭐⭐⭐ | sí (pages.dev) | ⭐⭐⭐⭐⭐ | Mejor rendimiento global |

---

## 🔧 Desarrollo Local

Para probar localmente antes de desplegar:

```bash
cd /Users/ainara/Proyectos/curso_agents

# Opción 1: Con Node.js
node dev-server.js
# Abrir http://localhost:3000

# Opción 2: Con Python
python3 -m http.server 3000
# Abrir http://localhost:3000

# Opción 3: Con Live Server (VS Code)
# Instalar extensión "Live Server"
# Click derecho en index.html > Open with Live Server
```

---

## 📊 Datos Accesibles

El catálogo consume datos de Supabase Cloud:

- **URL Base:** https://kyckwehxtyjggpsclxbc.supabase.co/rest/v1
- **Endpoints:**
  - `/levels` - 4 niveles formativos
  - `/families` - 4 familias profesionales
  - `/programs` - 18 programas
  - `/modules` - 134 módulos
- **Autenticación:** API key anon (lectura pública)

---

## 🎨 Personalización

### Cambiar colores
Editar las variables CSS al inicio del `<style>`:
```css
:root {
    --burgundy: #7A1020;      /* Primario */
    --navy: #003A70;          /* Secundario */
    /* ... más colores */
}
```

### Cambiar textos
Buscar en el HTML:
- `<h1>` para el título principal
- `label for="level-filter"` para etiquetas

### Agregar más datos
Los datos se cargan dinámicamente desde Supabase, no hay limite.

---

## 📞 Soporte

- **Supabase Dashboard:** https://app.supabase.com/project/kyckwehxtyjggpsclxbc
- **Documentación Supabase:** https://supabase.com/docs
- **Repositorio local:** `/Users/ainara/Proyectos/curso_agents`

---

**Última actualización:** 15 de Septiembre de 2026
**Estado:** ✅ Listo para producción
