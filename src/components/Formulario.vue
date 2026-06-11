<script setup>
import { ref, watch } from "vue";

const nombreData = ref("");
const edadData = ref(0);
const biografiaData = ref("");
const nivelData = ref("");
const tecnologiaData = ref([]);
const paisData = ref("");

watch(edadData, () => {
  if (edadData.value < 1) {
    edadData.value = 1;
  } else if (edadData.value > 5) {
    edadData.value = 5;
  }
});

const niveles = ["junior", "semi senior", "senior"];
const tecnologias = ["Vue", "React", "Angular", "Svelte"];
const paises = [
  { code: "CL", name: "Chile" },
  { code: "AR", name: "Argentina" },
  { code: "PE", name: "Peru" },
];

const enviarFormulario = () => {

    const dataForm = {
      nombre: nombreData.value,
      edad: edadData.value,
      biografia: biografiaData.value,
      nivel: nivelData.value,
      tecnologia: tecnologiaData.value,
      pais: paisData.value,
    }

    console.log(JSON.stringify(dataForm, null, 2));

};
</script>

<template>
  <div>
    <div class="page">


      <form @submit.prevent="enviarFormulario" class="formulario">
        <h2>Formulario Registro Perfil</h2>

        <div class="block">
          <label for="nombre">Nombre</label>
          <input type="text" v-model.trim="nombreData" />
        </div>

        <div class="block">
          <label for="edad">Edad</label>
          <input
            id="edad"
            type="number"
            v-model.number="edadData"
          />
        </div>

        <div class="block">
          <label for="biografia">Biografía</label>
          <textarea v-model.lazy="biografiaData"></textarea>
        </div>

        <div class="block">
          <p>nivel</p>
          <label v-for="ni in niveles" :key="ni" :for="ni">
            <input
              :id="ni"
              v-model="nivelData"
              type="radio"
              :name="ni"
              :value="ni"
            />
            {{ ni }} <br />
          </label>
        </div>

        <div class="block">
          <p>Tecnologías</p>
          <label v-for="tec in tecnologias" :key="tec" :for="tec">
            <input
              :id="tec"
              v-model="tecnologiaData"
              type="checkbox"
              :name="tec"
              :value="tec"
            />
            {{ tec }} <br />
          </label>
        </div>

        <div class="block">
          <label for="pais">Pais</label>
          <select name="pais" id="pais" v-model="paisData">
            <option>Seleccione un pais</option>
            <option v-for="p in paises" :value="p.code" :key="p.code">
              {{ p.name }}
            </option>
          </select>
        </div>

        <div class="block">
          <button type="submit">Enviar</button>
        </div>
      </form>

      <pre class="resumen">
Resumen:

Nombre: {{ nombreData }}
Edad: {{ edadData }}
Biografia: {{ biografiaData }}
Nivel: {{ nivelData }}
Tecnologia: {{ tecnologiaData }}
Pais: {{ paisData }}
            </pre
      >
    </div>
  </div>
</template>

<style scoped>
.page {
  display: flex;
}
.formulario {
  background-color: #ffffff;
  padding: 30px;
  margin: 10px;
  border-radius: 10px;
  width: 50%;
}
.resumen {
  background-color: #8dbed8;
  padding: 30px;
  margin: 10px;
  border-radius: 10px;
  width: 50%;
}

button {
  margin: 10px;
  padding: 10px 20px;
  border-radius: 4px;
  border: none;
  border: 2px solid #6d8dbc;
  background-color: #a4bfe9;
  color: #000;
  cursor: pointer;
}

button:hover {
  filter: brightness(0.6);
}

input[type="text"] {
  padding: 10px;
  width: 100%;
  border-radius: 4px;
  border: none;
  background-color: #ede6e0;
  cursor: pointer;
  border: 2px solid #999;
}

input[type="text"]:focus {
  box-shadow: 0px 0px 6px 2px #999;
}

input[type="number"] {
  padding: 10px;
  width: 60px;
  border-radius: 4px;
  border: none;
  background-color: #ede6e0;
  cursor: pointer;
  border: 2px solid #999;
}

textarea {
  padding: 10px;
  width: 200px;
  height: 100px;
  border-radius: 4px;
  border: none;
  background-color: #ede6e0;
  cursor: pointer;
  border: 2px solid #999;
  resize: none;
  font-family: sans-serif;
}

.block {
  display: flex;
  gap: 10px;
  border: 2px solid #326fba;
  margin: 10px;
}
</style>
