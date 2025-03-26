<script setup>
import { computed } from 'vue'

const props = defineProps({
  items: {
    type: Array,
    required: true
  }
})

const emit = defineEmits(['removeFromCart', 'sendText'])

// Computed property to calculate total price
const totalPrice = computed(() => {
  return props.items.reduce((sum, item) => sum + item.price, 0)
})

/**
 * Computar el precio total menos el descuento del 30%
 * @returns {number} Precio total menos el descuento
 */
const totalDescuento = computed(() => {
  return props.items.reduce((sum, item) => sum + item.price * 0.7, 0)
})

// Computed property to count total items
const itemCount = computed(() => props.items.length)

const removeItem = (item) => {
    sendText()
    emit('removeFromCart', item)
}

/**
 * Enviar texto al portapapeles
 * @returns {void}
 * @throws {Error} Error al copiar el texto
 */
const sendText = () => {
  const text = totalDescuento.value.toFixed(2)
  navigator.clipboard.writeText(text).then(() => {
    console.log('Texto copiado al portapapeles: ', text)
  }).catch(err => {
    console.error('Error al copiar el texto: ', err)
  })
  emit('sendText', text)
}

</script>

<template>
  <div class="shopping-cart">
    <h2>Shopping Cart ({{ itemCount }})</h2>
    <div v-if="items.length === 0" class="empty-cart">
      Your cart is empty
    </div>
    <div v-else>
        <button @click="sendText">Ver desceunto</button>
        <div v-for="item in items" :key="item.id" class="cart-item">
            <span>{{ item.name }}</span>
            <span>${{ item.price.toFixed(2) }}</span>
            <button @click="removeItem(item)">Remove</button>
        </div>
        <div class="cart-total">
            <strong>Total: ${{ totalPrice.toFixed(2) }}</strong>
        </div>
    </div>
  </div>
</template>

<style scoped>
.shopping-cart {
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 4px;
  margin: 20px;
}
.cart-item {
  display: flex;
  justify-content: space-between;
  padding: 10px 0;
  border-bottom: 1px solid #eee;
}
.cart-total {
  margin-top: 20px;
  text-align: right;
}
.empty-cart {
  text-align: center;
  color: #666;
  padding: 20px;
}
.discount strong {
  font-style: italic;
  font-weight: 100;
  font-size: 1em;
}

</style>