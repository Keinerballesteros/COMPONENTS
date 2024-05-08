<script setup>

import { ref } from "vue";

let number = ref(0);
let time = ref(0);
let interval
function add() {
    if(number.value == 0){
        interval = setInterval(() => {
            time.value++
        }, 1000)
    }
    number.value++
    if(number.value == 10){
        clearInterval(interval)
    }
}
</script>

<template>
    <div v-show="number > 0" class="float-right mr-3 rouded inline-block py-1 px-2 bg-slate-500">
        Tiempo: {{ time }}
    </div>
    <div @click="add"
        class="bg-green-600/50 text-white py-1 px-2 rounded-lg w-12 text-center mt-10 mx-auto hover:cursor-pointer hover:bg-slate-300 select-none">
        {{ number }}
    </div>
    <div v-if="number ==0" class="bg-orange-300/20 rounded w-48 mx-auto mt-8 py-1 px-2 text-center">
        ¿Clickear? ¡O miedo! ✌
    </div>
    <div v-else class="bg-green-300/20 rounded w-48 mx-auto mt-8 py-1 px-2 text-center">
        ¡GO!  
        ¡GO!  
        ¡GO!  🐢
    </div>
</template>