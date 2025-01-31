<template>
    <div>
      <h2 class="text-xl">{{ word }}</h2>
    </div>
    
</template>

<script setup>
import { ref } from 'vue';
const words = [
  "apple", "banana", "cherry", "date", "elephant", 
  "flame", "grape", "honey", "igloo", "jungle", 
  "kiwi", "lemon", "monkey", "notebook", "orange", 
  "piano", "quilt", "rose", "sunflower", "tree", 
  "umbrella", "violet", "watermelon", "xylophone", 
  "yarn", "zebra", "airplane", "balloon", "candle", 
  "dinosaur", "elephant", "forest", "guitar", "harp"
];
const num = Math.floor(Math.random()*words.length)
let word =ref(words[num])
function scrambleWords(){
  word.value = word.value.split("").sort(() => 0.5 - Math.random()).join('');
}
scrambleWords()

</script>

<style scoped>

</style>
