<script setup>
import { ref } from 'vue';

const val = ref('helloooooooooooo')


const logs = ref([])

const funSaludo = () => {
    alert('funcion demo')
    val.value = 'hola'
}



const marcarFavorito = (id) => {
    console.log("marcar favorito" + id)
    logs.value.unshift("accion marcar favorito" + id)
}

const seleccionarTarjeta = (id) => {
    console.log("seleccionar tarjeta" + id)
}
</script>



<template>
  <div class="centro">
    <h1>Centro de Eventos</h1>
    

    <p>{{val}}</p>

    <button @click="val = 'hola'">
        cambiar hello
    </button>
    
    <button @click="funSaludo">
        saludo
    </button>
    

    <form>
        <input type="text">
        <button>Enviar</button>
    </form>

    <div class="tarjetas-centro">
        
        
        <div @click="seleccionarTarjeta(1)" class="tajeta-centro">
            <h4>Evento 1 .stop en boton</h4>
            <button @click.stop="marcarFavorito(1)">favorito</button>
        </div>


        <div  @click.capture="seleccionarTarjeta(2)" class="tajeta-centro">
            <h4>Evento 2 .capture en tarjeta</h4>
            <button @click="marcarFavorito(2)">favorito</button>
        </div>


        <div   @click="seleccionarTarjeta(3)" class="tajeta-centro">
            <h4>Evento 3 sin modificador</h4>
            <button @click="marcarFavorito(3)">favorito</button>
        </div>
    </div>





    <div class="log">
        <p v-for="item in logs" :key="item">
            {{ item }}
        </p>
    </div>
  </div>
</template>



<style scoped>

.centro{
  width: 100%;
  height: auto;
  background-color: #e2a1e6;
  padding: 10px;
  margin: 10px;
  border-radius: 10px;
}

button{
  margin: 10px;
  padding: 10px;
  border-radius: 4px;
  border: none;
  background-color: #cdcbc9;
  cursor: pointer;
}

button:hover{
  background-color: #959594;
}

input[type="text"]{
  margin: 10px;
  padding: 10px;
  width: 200px;
  border-radius: 4px;
  border: none;
  background-color: #ede6e0;
  cursor: pointer;
  box-shadow: 0px 0px 6px 2px #999 inset;
}

input[type="text"]:focus{
  box-shadow: 0px 0px 6px 2px #999;
}


.tarjetas-centro{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;

  width: fit-content;
  height: auto;
  background-color: #e3e3e3;
  padding: 10px;
  margin: 10px;
  border-radius: 10px;
}


.tajeta-centro{
  width: 200px;
  height: auto;
  background-color: #75d4d9;
  padding: 10px;
  margin: 10px;
  border-radius: 10px;
}
</style>