# Estructura de CSS del API Client

Los estilos del API Client han sido separados en múltiples archivos para facilitar el mantenimiento y la personalización.

## 📁 Archivos CSS

### 1. `api-client-variables.css`
**Variables CSS y configuración de temas**
- Define todas las variables CSS para colores, espaciado, tipografía
- Incluye configuración para tema oscuro automático
- Clases de utilidad para métodos HTTP y estados
- Variables para fácil personalización

### 2. `api-client.css`
**Estilos principales**
- Estilos base del componente API Client
- Layout principal con CSS Grid
- Estilos de formularios y botones
- Paneles de request y response
- Syntax highlighting para JSON
- Animaciones y transiciones

### 3. `api-client-responsive.css`
**Estilos responsivos**
- Media queries para diferentes tamaños de pantalla
- Adaptaciones para tablets (768px)
- Adaptaciones para móviles (480px)
- Adaptaciones para pantallas muy pequeñas (320px)

### 4. `documentation-dark-theme.css` ✨ **NUEVO**
**Tema oscuro unificado con el API Client**
- Tema oscuro unificado con las mismas variables del API Client
- Estilos específicos para vistas de documentación
- Consistencia visual completa entre API Client y documentación
- Syntax highlighting para Markdown
- Estilos para páginas de error
- Responsive design adaptado

## 🎨 Personalización

### Cambiar colores principales
Edita `api-client-variables.css` o `documentation-dark-theme.css`:
```css
:root {
    --primary-color: #tu-color-primario;
    --success-color: #tu-color-exito;
    --error-color: #tu-color-error;
    /* ... más variables */
}
```

### Cambiar fuentes
```css
:root {
    --font-family-primary: 'Tu-Fuente', sans-serif;
    --font-family-mono: 'Tu-Fuente-Mono', monospace;
}
```

## 🌙 Tema Oscuro Unificado

El sistema ahora cuenta con un tema oscuro completamente unificado entre:
- **API Client** (`api-client-*.css`)
- **Documentación** (`documentation-dark-theme.css`)

### Características del tema unificado:
- ✅ Misma paleta de colores en toda la aplicación
- ✅ Variables CSS compartidas
- ✅ Consistencia visual completa
- ✅ Syntax highlighting unificado para JSON y Markdown
- ✅ Experiencia de usuario coherente

### Archivos que usan el tema unificado:
- `resources/views/api-client.blade.php` → API Client principal
- `resources/views/documentation/markdown.blade.php` → Documentación Markdown
- `resources/views/documentation/not-found.blade.php` → Páginas de error 404

## 🔧 Uso en Blade

En tu vista Blade, incluye los archivos en este orden:
```html
<!-- Variables primero -->
<link rel="stylesheet" href="{{ asset('css/api-client-variables.css') }}">
<!-- Estilos principales -->
<link rel="stylesheet" href="{{ asset('css/api-client.css') }}">
<!-- Estilos responsivos al final -->
<link rel="stylesheet" href="{{ asset('css/api-client-responsive.css') }}">
```

## 📱 Breakpoints responsivos

- **Desktop**: > 768px (layout de 2 columnas)
- **Tablet**: ≤ 768px (layout de 1 columna)
- **Mobile**: ≤ 480px (espaciado reducido)
- **Small Mobile**: ≤ 320px (elementos más compactos)

## 🎯 Clases de utilidad disponibles

### Métodos HTTP
```css
.method-get      /* Verde para GET */
.method-post     /* Azul para POST */
.method-put      /* Naranja para PUT */
.method-delete   /* Rojo para DELETE */
.method-patch    /* Púrpura para PATCH */
```

### Estados de respuesta
```css
.status-2xx      /* Verde para códigos 2xx */
.status-3xx      /* Amarillo para códigos 3xx */
.status-4xx      /* Rojo para códigos 4xx */
.status-5xx      /* Rojo para códigos 5xx */
```

### Animaciones
```css
.animate-pulse   /* Animación de pulso */
.animate-bounce  /* Animación de rebote */
.fade-in         /* Desvanecimiento de entrada */
```

### Espaciado
```css
.mt-xs, .mt-sm, .mt-md, .mt-lg, .mt-xl  /* Margin top */
.mb-xs, .mb-sm, .mb-md, .mb-lg, .mb-xl  /* Margin bottom */
.p-xs, .p-sm, .p-md, .p-lg, .p-xl       /* Padding */
```

## 🔄 Orden de carga recomendado

1. **Variables** (`api-client-variables.css`) - Define las variables CSS
2. **Principal** (`api-client.css`) - Usa las variables para estilos principales
3. **Responsivo** (`api-client-responsive.css`) - Media queries y adaptaciones

## 🌙 Soporte para tema oscuro

El sistema incluye soporte automático para tema oscuro basado en la preferencia del sistema:
```css
@media (prefers-color-scheme: dark) {
    /* Estilos automáticos para tema oscuro */
}
```

## ⚡ Optimización

- **Variables CSS** para mejor rendimiento y mantenimiento
- **Archivos separados** para carga selectiva
- **Media queries** optimizadas para diferentes dispositivos
- **Clases de utilidad** para reutilización

## 🔧 Desarrollo

Para agregar nuevos estilos:
1. Agrega variables en `api-client-variables.css` si es necesario
2. Implementa estilos principales en `api-client.css`
3. Agrega adaptaciones responsivas en `api-client-responsive.css`

## 📦 Archivos generados

```
public/css/
├── api-client-variables.css     # Variables y configuración
├── api-client.css              # Estilos principales
├── api-client-responsive.css   # Media queries responsivas
└── documentation-dark-theme.css # Tema oscuro unificado para documentación

public/js/
└── api-client.js              # JavaScript separado
```

Esta estructura modular facilita el mantenimiento, permite personalización fácil y mejora la organización del código CSS.
