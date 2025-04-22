<script setup>
</script>

<template>
  <div class="app-container">
    <nav class="nav-menu">
      <router-link to="/">Inicio</router-link>
      <router-link to="/shop">Tienda</router-link>
      <router-link to="/about">Sobre</router-link>
    </nav>
    <router-view></router-view>
  </div>
</template>

<style>
.app-container {
  min-height: 100vh;
  background-color: #242424;
  padding: 1rem;
}

.nav-menu {
  max-width: 1200px;
  margin: 0 auto 20px;
  padding: 1rem;
  background-color: black;
  border-radius: 13px;
  display: flex;
  gap: 20px;
  justify-content: center;
}

.nav-menu a {
  color: white;
  text-decoration: none;
  padding: 8px 16px;
  border-radius: 8px;
  transition: background-color 0.3s;
}

.nav-menu a:hover {
  background-color: #646cff;
}

.nav-menu a.router-link-active {
  background-color: #535bf2;
}
</style>
