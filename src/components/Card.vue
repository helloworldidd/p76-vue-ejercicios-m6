<script setup>
defineProps({
    text: {
        type: String,
        default: 'Hola soy una Card'
    }
})
</script>

<template>
  <div class="card">
    <p>{{ text }}</p>
  </div>
</template>

<style scoped>

.card{
  width: 200px;
  height: auto;
  background-color: #75d4d9;
  padding: 10px;
  margin: 10px;
  border-radius: 10px;
}

</style>