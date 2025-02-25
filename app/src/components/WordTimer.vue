<template>
    <div>
        <button class="btn btn-default"@click = allowGame();startCountdown() v-if="allowBool == false">Start Game</button>
    </div>
    <WordScramble  :counter="counter"/>
  
    <h2>Do thte thing before timer go bye</h2>
    <h2 v-if="allowBool == true" class="font-mono">{{ counter }}</h2>
    
</template>

<script setup>
import {ref} from 'vue'
import WordScramble from './WordScramble.vue'
import WordGuess from './WordGuess.vue'

let allowBool = ref(false)
function allowGame(){
    allowBool.value = true
}
let counter = ref(15) 
let interval = null 

function startCountdown() {
  if (interval) clearInterval(interval) 

  interval = setInterval(() => {
    if (counter.value > 0) {
      counter.value-- 
    } else {
      clearInterval(interval) 
    }
  }, 1000) 
}
</script>

<style  scoped>

</style>