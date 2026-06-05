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
  <div>

    <p>Nombre: {{ mascota.nombre }}</p>
    <p>Tipo: {{ mascota.tipo }}</p>
    <p>Edad: {{ mascota.edad }}</p>
    <p>vacunado: 
      <span v-if="mascota.vacunado" class="ok"> si vacunado</span>
      <span v-else class="error"> no vacunado</span>
    </p>

    <p
      v-for="caracteristica in mascota.caracteristicas"
      :key="caracteristica"
    >
      {{ caracteristica }}
    </p>
  
  
  </div>
</template>

<style scoped>

p{
  font-family: sans-serif;
  font-weight: bold;
  font-size: 18px
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

</style>