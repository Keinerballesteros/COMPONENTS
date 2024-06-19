<script setup>
import { ref } from 'vue';

// Define las referencias reactivas
let img = ref('');
let name = ref('');
let msg = ref('');
let direction = ref('');
let value = ref(false);

// Función para cargar los datos de la API
async function fetchData() {
    const response = await fetch('https://thesimpsonsquoteapi.glitch.me/quotes?count=num');
    const data = await response.json();
    img.value = data[0].image;
    name.value = data[0].character;
    msg.value = data[0].quote;
    direction.value = data[0].characterDirection;
    
    value.value = direction.value === "Right";
}

// Llama a fetchData al iniciar
fetchData();

// Función para recargar los datos
async function reload() {
    await fetchData();
}

</script>

<template>
    <div class="flex flex-row " :class="{'flex-row-reverse': value}">
        <img :src="img" alt="">
        <div>
            <h6>{{ name }}</h6>
            <p>{{ msg }}</p>
            <button @click="reload">Cambiar</button>
        </div>
    </div>
</template>