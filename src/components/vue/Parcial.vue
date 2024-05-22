  <script >
  import {ref} from 'vue' 
  export default {
    props: {
      titulo: String,
      conteudo: String,
    },
  };
  let contador = ref(0);
  function view(){
    contador.value++;
    console.log(contador);
  }
  </script>

  
<template>
    <div class="flex justify-center flex-col">
      <button @click="view()" class="w-[500px] p-2 bg-black text-white mx-auto">Click</button>
      <h1 class="font-semibold text-2xl mx-auto">{{ titulo }}</h1>
      <h2 class="mx-auto text-xl font-bold">{{ conteudo }}</h2>
    </div>
  </template>
  