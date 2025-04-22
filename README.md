# Vue E-commerce Practice

Este es un proyecto de práctica de Vue.js que implementa una tienda virtual simple con características reactivas usando Vue 3 y Vite.

## Características Principales

### 1. Sistema de Navegación
- Implementación de Vue Router para navegación entre páginas
- Rutas configuradas:
  - `/`: Página de inicio con mensaje de bienvenida
  - `/shop`: Tienda virtual con productos y carrito
  - `/about`: Página informativa sobre la tienda
- Menú de navegación mejorado con indicador de página activa
- Transiciones suaves entre páginas

### 2. Interfaz de Usuario Mejorada
- Nuevo componente HeaderTitle con fondo distintivo
- Diseño mejorado del filtro de precios con bordes decorativos
- Estilo consistente en todas las vistas
- Tema oscuro optimizado con acentos en #646cff

### 3. Catálogo de Productos
- Lista de productos con precios
- Filtrado dinámico por rango de precios (mínimo y máximo)
- Contador de productos disponibles según filtros
- Productos predefinidos: Laptop, Smartphone, Headphones, Mouse, Keyboard

### 4. Carrito de Compras
- Añadir/remover productos
- Contador de items en tiempo real
- Cálculo automático del total
- Sistema de descuento del 30%
- Interfaz simplificada y más intuitiva

## Estructura del Proyecto
```
vue-computed-practice/
├── src/
│   ├── components/
│   │   ├── HeaderTitle.vue    # Componente de título mejorado
│   │   ├── ProductList.vue    # Lista de productos con filtros
│   │   └── ShoppingCart.vue   # Carrito de compras simplificado
│   ├── views/
│   │   ├── HomeView.vue      # Página de inicio
│   │   ├── ShopView.vue      # Vista principal de la tienda
│   │   └── AboutView.vue     # Nueva página "Acerca de"
│   ├── router/
│   │   └── index.js         # Configuración de rutas actualizada
│   ├── App.vue              # Navegación mejorada
│   ├── main.js             # Punto de entrada
│   └── style.css           # Estilos globales actualizados
├── package.json
└── vite.config.js
```

## Componentes Actualizados

### App.vue
- Nueva barra de navegación con diseño mejorado
- Indicador visual de página activa
- Estructura responsive actualizada

### HeaderTitle.vue
- Diseño modernizado con fondo #646cff
- Subtítulo informativo
- Personalizable mediante props
- Margen inferior optimizado

### Views
- **HomeView**: Página de bienvenida con enlace a la tienda
- **ShopView**: Vista principal con diseño mejorado
- **AboutView**: Nueva página con información de la tienda

## Características de Diseño
- Tema oscuro con fondo #242424
- Acentos en #646cff para elementos interactivos
- Layout responsive mejorado
- Máximo ancho de 1200px
- Bordes redondeados consistentes
- Diseño modular y reutilizable
- Transiciones suaves en interacciones

## Tecnologías Utilizadas
- Vue 3
- Vue Router 4
- Vite
- CSS Modules
- Computed Properties
- Component Composition API

## Cómo Ejecutar el Proyecto

1. Instalar dependencias:
```bash
npm install
```

2. Ejecutar en modo desarrollo:
```bash
npm run dev
```

3. Construir para producción:
```bash
npm run build
```

## Próximas Mejoras Posibles
- Persistencia de datos
- Más opciones de filtrado
- Sistema de categorías
- Gestión de inventario
- Proceso de checkout
- Mejoras en el diseño responsive
- Integración con backend
- Sistema de autenticación
- Historial de pedidos

## Notas de Desarrollo
- El proyecto utiliza la Composition API de Vue 3
- Los precios se muestran con 2 decimales usando toFixed(2)
- Diseño responsive optimizado para múltiples dispositivos
- Sistema de descuento del 30% en el carrito
- Nueva navegación entre páginas con Vue Router 4
- Componentes modularizados para mejor mantenimiento
- Estilos consistentes en toda la aplicación
