<script setup>


const mascota = {
  nombre: 'Luna',
  tipo: 'Gato',
  edad: 4,
  vacunado: true,
  foto: 'https://mis-imagenes-fake.com/sailor-moon/luna.png',
  caracteristicas: ['Sabia', 'Protectora', 'Misteriosa']
}


</script>

<template>
  <div class="ficha">

    <p> <strong>Nombre:</strong> {{ mascota.nombre }}</p>
    <p> <strong>Tipo:</strong>  {{ mascota.tipo }}</p>
    <p> <strong>Edad:</strong> {{ mascota.edad }}</p>
    <p> <strong> Vacunado:</strong>
      <span v-if="mascota.vacunado" class="ok"> si vacunado</span>
      <span v-else class="error"> no vacunado</span>
    </p>
    <p> <strong> Caracteristicas:</strong> </p>
    <ul>
      <li
      v-for="caracteristica in mascota.caracteristicas"
      :key="caracteristica"
      >
      {{ caracteristica }}
    </li>
    </ul>
  
  
  </div>
</template>

<style scoped>

.ficha{
  width: 200px;
  height: auto;
  background-color: #f5f5f5;
  padding: 10px;
  margin: 10px;
  border-radius: 10px;
}
p{
  font-family: sans-serif;
  font-size: 16px
}

.ok{
  color: green
}
.alert{
  color: #f8bd0d
}
.error{
  color: red
}



ul{
  list-style-position: inside;
}
</style>