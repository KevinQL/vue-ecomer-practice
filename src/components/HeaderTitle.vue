<script setup>
    // const title = 'Welcome to Our Virtual Store'

    const propos = defineProps({
        title: {
            type: String,
            default: ''
        }
    })

</script>

<template>
    <header class="header-title">
        <h1>{{ title }}</h1>
        <p>Explore our selection of products at the best prices</p>
    </header>
</template>

<style scoped>
    .header-title {
        text-align: center;
        background-color: #646cff;
        color: white;
        padding: 20px;
        border-radius: 8px;
        margin-bottom: 20px;
    }

    .header-title h1 {
        margin: 0;
        font-size: 2rem;
    }
</style>
