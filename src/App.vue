<script setup>
import { ref, computed } from 'vue'
import ProductList from './components/ProductList.vue'
import ShoppingCart from './components/ShoppingCart.vue'

const cartItems = ref([])
const priceFilter = ref({
  min: 0,
  max: 1000
})
const textportapapeles = ref('...')

// Computed property for total items in cart
const cartItemCount = computed(() => cartItems.value.length)

const addToCart = (product) => {
  cartItems.value.push(product)
}

const removeFromCart = (product) => {
  const index = cartItems.value.findIndex(item => item.id === product.id)
  if (index !== -1) {
    cartItems.value.splice(index, 1)
  }
}

const sendText = (text) => {
  textportapapeles.value = text;
}

</script>

<template>
  <div class="app">
    <h1>Vue Shop with Computed Properties</h1>
    
    <div class="price-filter">
      <h3>Price Filter</h3>
      <span style="color: yellowgreen;"><small> DESCUENTO {{ textportapapeles }}</small></span>
      <div class="filter-inputs">
        <label>
          Min Price:
          <input type="number" v-model="priceFilter.min" min="0">
        </label>
        <label>
          Max Price:
          <input type="number" v-model="priceFilter.max" min="0">
        </label>
      </div>
    </div>

    <div class="main-content">
      <ProductList 
        :min-price="Number(priceFilter.min)" 
        :max-price="Number(priceFilter.max)"
        @add-to-cart="addToCart"
      />
      <ShoppingCart 
        :items="cartItems"
        @remove-from-cart="removeFromCart"
        @send-text="sendText"
      />
    </div>
  </div>
</template>

<style scoped>
.app {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  background-color: black;
  border-radius: 13px;
}

.price-filter {
  margin-bottom: 20px;
}

.filter-inputs {
  display: flex;
  gap: 20px;
}

.filter-inputs label {
  display: flex;
  gap: 10px;
  align-items: center;
}

.main-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 20px;
}

input[type="number"] {
  padding: 5px;
  width: 100px;
}
</style>
