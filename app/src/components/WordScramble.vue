<template>
  <div class="">
    <WordGuess
      :scrambled="word"
      :correct="correctWord"
      :word_list="words"
      :word_next="scrambleWords"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue'
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
  'tariffs',
  'tree',
  'trump',
  'umbrella',
  'violet',
  'watermelon',
  'whalen',
  'xylophone',
  'yarn',
  'zebra',
]

function scrambleWords() {
  const num = Math.floor(Math.random() * words.length)
  let word = ref(words[num])
  const correctWord = words[num]
  word.value = word.value

    .split('')
    .sort(() => 0.5 - Math.random())
    .join('')
  console.log(word.value)
}
scrambleWords()
</script>

<style scoped></style>
