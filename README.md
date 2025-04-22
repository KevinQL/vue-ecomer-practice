# Vue E-commerce Practice

Este es un proyecto de práctica de Vue.js que implementa una tienda virtual simple con características reactivas usando Vue 3 y Vite.

## Características Principales

### 1. Catálogo de Productos
- Lista de productos con precios
- Filtrado dinámico por rango de precios (mínimo y máximo)
- Contador de productos disponibles según filtros
- Productos predefinidos: Laptop, Smartphone, Headphones, Mouse, Keyboard

### 2. Carrito de Compras
- Añadir/remover productos
- Contador de items en tiempo real
- Cálculo automático del total
- Sistema de descuento del 30%
- Mensaje personalizable en el carrito
- Función para copiar el descuento al portapapeles

### 3. Características Técnicas
- Implementación de Vue 3 con `<script setup>`
- Uso de Computed Properties para cálculos reactivos
- Sistema de comunicación entre componentes con props y eventos
- Estilizado con CSS modular (scoped)
- Diseño responsive con grid layout

## Estructura del Proyecto
```
vue-computed-practice/
├── src/
│   ├── components/
│   │   ├── ProductList.vue    # Lista de productos con filtros
│   │   └── ShoppingCart.vue   # Carrito de compras con descuentos
│   ├── App.vue               # Componente principal
│   ├── main.js              # Punto de entrada
│   └── style.css            # Estilos globales
├── package.json
└── vite.config.js
```

## Componentes

### App.vue
- Componente principal que gestiona el estado global
- Manejo del carrito de compras
- Sistema de filtros de precio
- Layout principal con grid

### ProductList.vue
- Muestra productos disponibles
- Implementa filtrado por precio
- Emite eventos para agregar productos al carrito

### ShoppingCart.vue
- Gestiona items en el carrito
- Calcula totales y descuentos
- Permite remover productos
- Muestra mensajes personalizados

## Características de Diseño
- Tema oscuro con fondo negro
- Layout responsive
- Máximo ancho de 1200px
- Bordes redondeados
- Diseño modular y reutilizable

## Tecnologías Utilizadas
- Vue 3
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
- Checkout process
- Responsive design improvements

## Notas de Desarrollo
- El proyecto utiliza la Composition API de Vue 3 para mejor organización del código
- Los precios se muestran con 2 decimales usando toFixed(2)
- El diseño es responsive y adaptable a diferentes tamaños de pantalla
- Se implementó un sistema de descuento del 30% en el carrito
