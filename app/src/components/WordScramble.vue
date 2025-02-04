<template>
  <div class="">
    <h2 class="text-white text-xl" >{{ word }}</h2>
    <WordGuess :scrambled="word" :correct="correctWord"/>
  </div>
</template>

<script setup>
import { ref,reactive } from 'vue'
import WordGuess from './WordGuess.vue'
const words = [
  'airplane',
  'balloon',
  'banana',
  'candle',
  'cherry',
  'date',
  'dinosaur',
  'elephant',
  'elephant',
  'flame',
  'forest',
  'grape',
  'guitar',
  'harp',
  'honey',
  'igloo',
  'jungle',
  'kiwi',
  'lemon',
  'monkey',
  'notebook',
  'orange',
  'piano',
  'quilt',
  'rose',
  'sunflower',
  'tree',
  'umbrella',
  'violet',
  'watermelon',
  'xylophone',
  'yarn',
  'zebra',
]

const num = Math.floor(Math.random() * words.length)
let word = ref(words[num])
const correctWord=words[num]
function scrambleWords() {
  word.value = word.value
    .split('')
    .sort(() => 0.5 - Math.random())
    .join('')
  console.log(word.value)
}
scrambleWords()


</script>

<style scoped></style>
