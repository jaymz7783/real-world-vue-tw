<script setup>
import { ref } from 'vue'
import ProductDisplay from './components/ProductDisplay.vue'

const cart = ref([])
const premium = ref(true)
  
function updateCart(id) {
  cart.value.push(id)
}
</script>

<template>
<!--  the brackets allow for custom attributes, alternatively to use tw sizes these are the attributes
these aren't exactly the same but are close
h-[60px] -> h-16
mb-[25px] -> mb-6
from-[#16c0b0] to-[#84cf6a] -> from-teal-400 to-green-500
-->
  <div class="h-16 mb-6 bg-gradient-to-r from-ocean to-leaf">
  </div>
  <div class="my-6 mx-24 p-7 mist-border-1 bg-cloud float-right">
    Cart({{ cart.length }})
  </div>
  <product-display :premium="premium" @add-to-cart="updateCart"></product-display>
</template>

<style scoped>

</style>
