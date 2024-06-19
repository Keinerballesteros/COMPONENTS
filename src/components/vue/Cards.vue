<script setup>
import {ref} from 'vue';
const dataJSON = ref()
const right = "direction Right"
const left = "direction Left"
let value = false
let direction

const data2 = await fetch('https://thesimpsonsquoteapi.glitch.me/quotes?count=num').then(res => res.json())
dataJSON.value = data2
direction = dataJSON.value[0].characterDirection;
    if(direction == "Left"){
        value = true;
        console.log(direction);
        console.log(value);
    }


/*
async function reload(){
    await getData()
}
    */
</script>
<template>
<div class="flex justify-center items-center">
    <div class="flex py-4 px-4 w-[500px] h-[250px] bg-white/60 flex-row border-4 border-yellow-700 rounded-lg mt-4" :class="{'flex-row-reverse': value}">
        <div class="ml-2 flex flex-row" >
            <img :src="dataJSON[0].image" alt="Simpsons Character" class="w-44 h-32 rounded-full border my-auto"/>
        </div>
        <div class="ml-4 flex-col flex">
            <p class="text-lg font-extrabold ">{{ dataJSON[0].character }}</p>
            <p class="text-lg font-bold mt-2">Quote: {{ dataJSON[0].quote }}</p>
            <!--<p class="text-lg font-bold mt-2">direction: {{ dataJSON[0].characterDirection }}</p>-->
            <button @click="reload" class="w-auto h-8 text-lg font-bold mt-2 text-white bg-black">Change</button>
        </div>
    </div>
</div>
</template>