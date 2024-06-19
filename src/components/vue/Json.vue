<script setup>
import jsonData from './data.json';
import { ref } from 'vue';

const dataJSON = ref()
console.log(jsonData);


async function getDataTwo(){
    const data = await fetch('https://jsonplaceholder.typicode.com/posts/1')
     dataJSON.value = await data.json()

    console.log(dataJSON)
}

getDataTwo()
</script>
<template>
<div class="text-center text-2xl font-extrabold ">
    {{ jsonData.Nombre }}
</div>
<div class="text-center text-2xl font-extrabold mt-5">

    {{ dataJSON.title }}

</div>



</template>