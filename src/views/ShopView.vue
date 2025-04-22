<script setup>
  import { ref, computed } from 'vue'
  import ProductList from '../components/ProductList.vue'
  import ShoppingCart from '../components/ShoppingCart.vue'
  import HeaderTitle from '../components/HeaderTitle.vue'


  const cartItems = ref([])
  const priceFilter = ref({
    min: 0,
    max: 1000
  })

  const totalDescuento = computed(() => {
    return cartItems.value.reduce((sum, item) => sum + item.price * 0.7, 0).toFixed(2)
  })

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
</script>


<template>
  <div class="shop">
    <HeaderTitle :title="String('Welcome to Our Virtual Store 2025')"/>
    
    <div class="price-filter">
      <h3>Price Filter</h3>
      
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

      <span style="color: #646cff;"><small> Descuento ${{ totalDescuento }} soles de {{ cartItemCount }} unidades</small></span>
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
    <router-link to="/" class="home-button">Volver al Inicio</router-link>
  </div>
</template>

<style scoped>
  .shop {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
    background-color: black;
    border-radius: 13px;
  }

  .price-filter {
    margin-bottom: 10px;
  }

  .filter-inputs {
    display: flex;
    gap: 20px;
    justify-content: center;
    border: 1px solid #646cff;
    padding: 10px;
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

  .home-button {
    display: inline-block;
    padding: 10px 20px;
    background-color: #646cff;
    color: white;
    text-decoration: none;
    border-radius: 8px;
    margin-top: 20px;
    transition: background-color 0.3s;
  }

  .home-button:hover {
    background-color: #535bf2;
  }
</style>