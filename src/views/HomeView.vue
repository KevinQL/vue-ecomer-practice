<script setup>
</script>

<template>
  <div class="home">
    <h1>Bienvenido a nuestra Tienda Virtual</h1>
    <p>Explora nuestra selección de productos con los mejores precios</p>
    <router-link to="/shop" class="shop-button">Ir a la Tienda</router-link>
  </div>
</template>

<style scoped>
.home {
  text-align: center;
  padding: 2rem;
  background-color: black;
  border-radius: 13px;
  margin: 20px auto;
  max-width: 1200px;
}

.shop-button {
  display: inline-block;
  padding: 10px 20px;
  background-color: #646cff;
  color: white;
  text-decoration: none;
  border-radius: 8px;
  margin-top: 20px;
  transition: background-color 0.3s;
}

.shop-button:hover {
  background-color: #535bf2;
}
</style>