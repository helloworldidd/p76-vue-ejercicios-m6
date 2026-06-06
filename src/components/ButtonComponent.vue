<script setup>

const emit = defineEmits([
    "botonClick"
])


const enviarEvento = () => {
    emit(
        "botonClick",
        "hola desde el hijo"
    )
}
</script>

<template>
    <div class="block">
        <button @click="enviarEvento">Enviar</button>
    </div>
</template>

<style scoped>

.block{
    display: flex;
    justify-content: center;
    padding: 80px;
}
button{
    background-color: #75d4d9;
    padding: 10px;
    border-radius: 10px;
    border: none;
    cursor: pointer;
}

</style>