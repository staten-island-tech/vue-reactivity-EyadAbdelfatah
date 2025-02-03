<template>
  <div>
    
    <form action="" method="get" class="text-white" @submit.prevent="submit">
      
      <input   placeholder="Type here" class="input input-bordered w-full max-w-xs" v-model="guess"/>
      <button class="btn" >Default</button>
      
    </form>
    <WordScramble ref="x"/>
    <h2 class="text-white">{{ guess }}</h2>

  </div>
</template>

<script setup >

import {ref} from 'vue'
import WordScramble from './WordScramble.vue';

const guess = ref('')

const x=ref(null)
const submit = () =>{
  console.log("submit is accessed")

  if(guess.value == x.value.correctWord){
    console.log("u right")
  }
  else{
    console.log("u suck")
  }
}
</script>

<style scoped></style>
