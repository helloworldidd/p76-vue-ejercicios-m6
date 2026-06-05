<script setup>


import CardList from './components/CardList.vue';
import NavBar from './components/NavBar.vue';
import Ficha from './components/Ficha.vue';
import CentroDeEventos from './components/CentroDeEventos.vue';


</script>

<template>

  <h1>Ejercicios</h1>

  <h2>Práctico 1</h2>
  <NavBar />
  <CardList />
  
  <h2>Práctico 2</h2>

  <Ficha />

  <h2>Práctico 3 (Pendiente)</h2>
  <CentroDeEventos />

  <h2>Práctico 4</h2>

  <h2>Práctico 5 (revisado en las ultimas clases)</h2>


</template>

<style scoped>

h2{
  margin: 100px 0 0 0;
  padding: 10px;
  font-family: sans-serif;
  height: auto;
  background-color: #75d4d9;
  border-top: 4px solid #3e7376;
  
}


</style>
