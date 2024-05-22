<script setup>
// import {ref } from "vue"
let listTheObjects = ["Martillo", "Casas", "Juguete", "Fútbol","Años"]
</script>

<template>
    <div class="mx-auto w-20 h-auto bg-slate-300 font-semibold mt-10">
        <div v-for="(list, index) in listTheObjects" :key="index" 
        class="px-2 mb-1 text-white" :class="{'bg-black': index % 2 !== 0, 'bg-blue-500/60':index % 2 === 0  }">
        {{ list }}
        </div>
    </div>
</template>