<script setup>
import {ref} from "vue"

defineProps({
  title: String,
  text: String,
  time: String
})

let value = ref(false)
let read = ref(false)
let button = ref('Marcar como leído')

function select(){
    if( value.value == true ){  
        
        value.value  = false
    }    
    else {
        value.value  = true
    }
}
function reading(){
    if( read.value == true){
        button.value = 'Marcar como leído'
        read.value = false
    }
    else{
        button.value = 'Marcar como no leído'
        read.value = true
    }
}
</script>
<template>

    <div class="w-[500px] h-[200px] bg-white shadow mx-auto mt-5 pt-3" @click="select()" :class="{'border-blue-700 border-4': value} ">
        <button class="flex ml-auto rounded-lg bg-transparent text-black font-medium mr-2 shadow p-2 hover:bg-black hover:text-white" @click="reading()">{{ button }}</button>
        <div class="flex flex-row ">
            <div v-if="read" class="size-8 flex ml-5 mt-8">
                <svg  xmlns="http://www.w3.org/2000/svg" class="text-green-600"  width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                    <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
                    <path d="M7 12l5 5l10 -10" />
                    <path d="M2 12l5 5m5 -5l5 -5"/>
                </svg>
            </div>
            <div v-else class="size-8 flex ml-5 mt-8 " >
                <svg xmlns="http://www.w3.org/2000/svg" class="text-yellow-500" width="44" height="44" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
                <path d="M3 12a9 9 0 1 0 18 0a9 9 0 0 0 -18 0"/>
                <path d="M12 8v4"/>
                <path d="M12 16h.01"/>
            </svg>
            </div>
           
            <div class="flex flex-col ml-10  mt-5">
            <h2 class="text-xl font-semibold text-black">{{ title }}</h2>
            <p class="mt-2 font-semibold text-black">{{text}}</p>
            <p class="mt-2 font-light text-slate-600">{{time }}</p>
            </div>
        </div>
    </div>

</template>