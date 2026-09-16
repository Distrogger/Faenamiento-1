# Dashboard Faenamiento Porcino v41

Dashboard interactivo para monitoreo de producción en línea de faenamiento porcino con datos en vivo desde Google Apps Script.

## Características

✅ **Datos en vivo** - Carga automática desde Google Apps Script con CORS habilitado  
✅ **12 KPIs** - Cards con alertas por color (verde/amarillo/rojo)  
✅ **7 Gráficos Plotly** - Cascada, Tendencia, Shewhart, Pareto, Box plots, Scatter, Heatmap  
✅ **Filtros dinámicos** - Fecha, línea, dotación, estándar, artículos  
✅ **Tema dark/light** - Automático + toggle manual  
✅ **Responsive** - Funciona en mobile y desktop  
✅ **Sin login** - Acceso público vía HTTPS  

## Stack

- HTML5 + Vanilla JavaScript
- Plotly.js v2.35+ (CDN jsDelivr)
- Fetch API (CORS habilitado)
- CSS Grid + Flexbox
- Español (es-EC)

## Requisitos para publicar en GitHub Pages

1. Cuenta de GitHub
2. Clonar/crear repositorio
3. Subir archivos a rama `main`
4. Activar GitHub Pages en Settings

## Instrucciones de uso local

### Opción 1: Servidor simple con Python

```bash
python -m http.server 8000
# Abre http://localhost:8000 en el navegador
```

### Opción 2: Servidor Node.js (http-server)

```bash
npm install -g http-server
http-server
# Abre http://localhost:8080 en el navegador
```

### Opción 3: Live Server (VSCode)

Instala la extensión "Live Server" de Ritwick Dey y haz clic derecho > "Open with Live Server"

## Publicar en GitHub Pages

### Paso 1: Crear repositorio

```bash
cd C:\Users\Usuario\Desktop\Faenamiento
git init
git add index.html
git commit -m "Initial commit: Dashboard v41"
```

### Paso 2: Conectar a GitHub

```bash
git remote add origin https://github.com/tu-usuario/faenamiento.git
git branch -M main
git push -u origin main
```

### Paso 3: Activar GitHub Pages

1. Ve a tu repositorio en GitHub
2. Settings → Pages
3. Source: main branch
4. Save
5. Tu sitio estará en: `https://tu-usuario.github.io/faenamiento/`

## URL del Apps Script (Fuente de datos)

El dashboard consume datos de:
```
https://script.google.com/macros/d/1rFwC9qxDGFG6e-h--nWN_SPgGqPGbwp9Y0BhLM-Ge6fS0DIw2a3hGEQW0SLeGsRZPrIqf9W4XiKG7hSE38JO5Y3ZS1n6Q4dSQ/usercache
```

**Nota**: Solo funciona vía HTTPS (GitHub Pages, Netlify, etc.). No funciona con `file://` local.

## Especificaciones técnicas

### KPIs calculados
- Cerdos procesados (total)
- Velocidad neta (cer/h)
- Velocidad bruta (cer/h)
- Cumplimiento estándar (%)
- Disponibilidad (%)
- Rendimiento (%)
- Peso promedio (kg/cer)
- Calidad de proceso (%)
- OEE (Overall Equipment Effectiveness)
- Kilos por hora
- Kilo h/h
- Dotación promedio

### Gráficos
1. **Cascada** - Pérdidas desde potencial a producción
2. **Tendencia semanal** - Velocidad neta vs bruta vs dotación
3. **Carta Shewhart** - Control estadístico de procesos
4. **Pareto** - Top 10 motivos de paradas
5. **Box plots** - Dotación vs velocidad
6. **Scatter** - Velocidad vs defectos
7. **Heatmap** - Semana × Día

## Formato de datos esperados

El Apps Script debe devolver JSON array con estos campos:

```json
[
  {
    "FECHA": "2026-09-15",
    "LAN": "Línea 1",
    "PERSONAL": 25,
    "CERDOS": 340,
    "DEFECTOS_PROCESO": 8,
    "KILOGRAMOS EN PIE": 8500,
    "HORAS_PRODUCTIVAS": 8,
    "HORAS_PROGRAMADAS": 8.5,
    "HORAS_PARAS_PLAN": 0.25,
    "HORAS_PARAS_NOPLAN": 0.25,
    "MOTIVOS": "Limpieza,Mantenimiento"
  }
]
```

## Problemas comunes

**❌ "Failed to fetch"**  
→ Estás abriendo el archivo local (`file://`). Solución: Sirve vía HTTP/HTTPS

**❌ Datos no cargan**  
→ Verifica que el Apps Script esté publicado con acceso "Cualquier usuario"

**❌ Gráficos no aparecen**  
→ Abre la consola (F12) y busca errores de Plotly

## Versión

- **v41** - Estándar 40 cerdos/hora, Pareto y Heatmap corregidos
- **Fecha**: 2026-09-15
- **Autor**: Distrogger (roggeras19@gmail.com)

## Licencia

Uso libre para monitoreo de producción interno

---

**URL de producción (después de publicar en GitHub Pages):**
```
https://tu-usuario.github.io/faenamiento/
```
