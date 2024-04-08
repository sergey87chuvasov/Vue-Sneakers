<script setup>
defineProps({
  title: String,
  description: String,
  imageUrl: String
})
</script>

<template>
  <img height="70" :src="imageUrl" />
  <h2>{{ title }}</h2>
  <p>{{ description }}</p>
</template>
