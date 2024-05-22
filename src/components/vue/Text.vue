<script setup>
import {  ref} from "vue";

defineProps({
  title: String,
  
})

let value = ref(false);
let number = ref(0);
function view(){
    number.value ++;
    console.log(number.value)
    if( value.value == true ){  
             
        value.value  = false
        
    
    }    
    else {
        value.value  = true
    }
}
</script>
<template>

    <div>
        <button @click="view()" class="bg-slate-600 w-full">Click</button>
        <p v-if="value">{{ title }}</p>
    </div>
</template>