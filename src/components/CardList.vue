<script setup>
import Card from './Card.vue';

import infoCards from '../data/cards.json'

const val = "card hola"
</script>

<template>
  
    <Card
      v-for="infoCard in infoCards"
      :key="infoCard.id"
      :text="infoCard.text"
    />

    



</template>

<style scoped>

</style>