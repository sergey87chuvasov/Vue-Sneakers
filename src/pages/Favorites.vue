<script setup>
import axios from 'axios'
import { ref, onMounted } from 'vue'

const favorites = ref([])

onMounted(async () => {
  try {
    const { data } = await axios.get('https://79d163bf6a39e896.mokky.dev/favorites')
  } catch (err) {}
})
</script>

<template>
  <h1>Мои закладки</h1>
</template>
