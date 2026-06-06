<script setup>


import CardList from './components/CardList.vue';
import NavBar from './components/NavBar.vue';
import Ficha from './components/Ficha.vue';
import CentroDeEventos from './components/CentroDeEventos.vue';
import ButtonComponent from './components/ButtonComponent.vue';




const mostrarMensaje = (txt) => {
  alert(txt)
}
</script>

<template>

<div class="contenedor">
  
| 
  <h1>Ejercicios</h1>


  <h2>Práctico 1</h2>
  <NavBar />
  <CardList />
  
  <h2>Práctico 2</h2>
  <Ficha />


  <h2>Práctico 3 (Pendiente)</h2>
  
  
  
  <h2>Práctico 4</h2>
  <CentroDeEventos />

  
  


  

  <h2>Práctico 5 (revisado en las ultimas clases)</h2>


  <h2>Extra defineEmits</h2>
  <ButtonComponent @botonClick="mostrarMensaje" />


</div>

</template>

<style scoped>


.contenedor{
  position: relative;
  display: block;
  border: 4px solid #3e7376;

}

h2{
  margin-top: 100px;
  padding: 10px;
  font-family: sans-serif;
  height: auto;
  background-color: #b7c9c9;
  border-top: 4px solid #3e7376;

}


</style>
