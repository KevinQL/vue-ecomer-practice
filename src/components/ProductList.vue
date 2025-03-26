<script setup>
import { ref, computed } from 'vue'

const props = defineProps({
  minPrice: {
    type: Number,
    default: 0
  },
  maxPrice: {
    type: Number,
    default: Infinity
  }
})

const emit = defineEmits(['addToCart'])

const products = ref([
  { id: 1, name: 'Laptop', price: 100 },
  { id: 2, name: 'Smartphone', price: 499.99 },
  { id: 3, name: 'Headphones', price: 99.99 },
  { id: 4, name: 'Mouse', price: 29.99 },
  { id: 5, name: 'Keyboard', price: 59.99 }
])

// Computed property to filter products by price range
const filteredProducts = computed(() => {
  return products.value.filter(product => 
    product.price >= props.minPrice && product.price <= props.maxPrice
  )
})

const countItem = computed(() => filteredProducts.value.length)

const addToCart = (product) => {
  emit('addToCart', product)
}
</script>

<template>
  <div class="product-list">
    <h2>Available Products ({{ countItem }})</h2>
    <div v-for="product in filteredProducts" :key="product.id" class="product-item">
      <h3>{{ product.name }} ♦</h3>
      <p>${{ product.price.toFixed(2) }}</p>
      <button @click="addToCart(product)">Add to Cart</button>
    </div>
  </div>
</template>

<style scoped>
.product-list {
  padding: 20px;
}
.product-item {
  border: 1px solid #ddd;
  margin: 10px 0;
  padding: 10px;
  border-radius: 4px;
}
</style>