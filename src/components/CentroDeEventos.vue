<script setup>
import { ref } from 'vue';


// ---------------------------------------

const logs = ref([])


const guardarLog = (infoLog) => {
  // if (logs.value.length < 4) {
  // }else {
  //   logs.value.pop()
  //   logs.value.unshift(infoLog)
    
  // }
  if(logs.value.length < 4){
    logs.value.unshift(infoLog) 
  }else {
    logs.value.pop()
    logs.value.unshift(infoLog)
    
  }
  console.clear()
  console.table(logs.value)

}

// ---------------------------------------


const busqueda = ref("")
const buscar = () => {
  if(busqueda.value.trim() === "") {
    busqueda.value = "busqueda vacia"
    guardarLog("formulario: busqueda vacia")
  }else {
    guardarLog("formulario: busqueda  " + busqueda.value.trim()) 
  }
}

const limpiar = () => {
  busqueda.value = ""
  guardarLog("formulario: limpiado")
}
// ---------------------------------------


const marcarFavorito = (id) => {
    guardarLog("tarjetas: marcar favorito" + id)
}

const seleccionarTarjeta = (id) => {
    guardarLog("tarjetas: seleccionar tarjeta" + id)
}

// ---------------------------------------


const textTips = ref("Mostrar tips")

const mostrarTips = () => {
  textTips.value = "tips Mostrados"
  guardarLog("tips: mostrar tips")
}


// ---------------------------------------

const posicionX = ref(0)
const onScroll = (event) => {
    posicionX.value = event.target.scrollTop.toFixed(0)
    guardarLog("scroll: posicion " + posicionX.value)
}


// ---------------------------------------

const abrirModal = () => {
    guardarLog("modal: abrir modal")
}


// ---------------------------------------










</script>



<template>
  <div class="centro">
    
    <h1>Centro de Eventos</h1>
    
    
    <br><br><br>
    <form @submit.prevent="buscar">
      <input
        v-model="busqueda"
        @keyup.esc="limpiar"
        placeholder="ingrese su busqueda"
        type="text">
      <button>Enviar</button>
      <div>{{busqueda}}</div>
    </form>
    
    
    <br><br><br>
    <div class="tarjetas-centro">

        <div @click="seleccionarTarjeta(1)" class="tajeta-centro">
            <h4>Evento 1</h4>
            <p>.stop en boton</p>
            <button @click.stop="marcarFavorito(1)">favorito</button>
        </div>


        <div  @click.capture="seleccionarTarjeta(2)" class="tajeta-centro">
            <h4>Evento 2</h4>
            <p>.capture en tarjeta</p>
            <button @click="marcarFavorito(2)">favorito</button>
        </div>

        
        <div   @click="seleccionarTarjeta(3)" class="tajeta-centro">
          <h4>Evento 3</h4>
          <p>sin modificador</p>
          <button @click="marcarFavorito(3)">favorito</button>
          <p>(burbujea)</p>
        </div>
      </div>

      
      <br><br><br>
      <button @click.once="mostrarTips">{{ textTips }}</button>


      <br>
      <br>
      <br>
    <h3>Testimonios</h3>
      <p>Scroll: {{posicionX}}</p>
      <ul @scroll.passive="onScroll" class="bloque-testimonios">
        <li>testimonio 1</li>
        <li>testimonio 2</li>
        <li>testimonio 3</li>
        <li>testimonio 4</li>
        <li>testimonio 5</li>
        <li>testimonio 6</li>
        <li>testimonio 7</li>
        <li>testimonio 8</li>
        <li>testimonio 9</li>
        <li>testimonio 10</li>
        <li>testimonio 11</li>
        <li>testimonio 12</li>
        <li>testimonio 13</li>
        <li>testimonio 14</li>
        <li>testimonio 15</li>
        <li>testimonio 16</li>
        <li>testimonio 17</li>
        <li>testimonio 18</li>
      </ul>


      <br>
      <br>
      <br>

      <a
        @click.prevent="abrirModal"
        href="http://google.com/">
        Terminos y condiciones
      </a>

      <br>
      <br>
      <br>


      <h3>Registro de Eventos( de los log)</h3>

      <p v-for="(e,index) in logs" :key="index">
          {{ e }}
      </p>

      <button @click="logs = []">limpiar logs</button>



  </div>
</template>



<style scoped>

.centro{
  background-color: #ffffff;
  padding: 30px;
  margin: 10px;
  border-radius: 10px;
}










form{
  border: 2px dashed #eee;
}
button{
  margin: 10px;
  padding: 10px 20px;
  border-radius: 4px;
  border: none;
  border: 2px solid #6d8dbc;
  background-color: #a4bfe9;
  color: #000;
  cursor: pointer;
}

button:hover{
  filter: brightness(0.6);
}

input[type="text"]{
  margin: 10px;
  padding: 10px;
  width: 200px;
  border-radius: 4px;
  border: none;
  background-color: #ede6e0;
  cursor: pointer;
  border: 2px solid #999;
}

input[type="text"]:focus{
  box-shadow: 0px 0px 6px 2px #999;
}





.tarjetas-centro{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;


  height: auto;
  background-color: #e1dcb7;
  padding: 10px;
}


.tajeta-centro{
  width: 120px;
  height: auto;
  background-color: #ffffff;
  padding: 10px;
  margin: 10px;
  border: 2px #000 solid;

}



.bloque-testimonios{
  height: 200px;
  background-color: #e1dcb7;
  list-style-position: inside;
  padding: 10px;
  overflow-y: scroll;

}
</style>