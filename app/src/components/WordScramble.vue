<template>
  <div class="">
    <WordGuess :scrambled="word" :correct="correctWord" @scramble="scrambleWords()" />
  </div>
</template>

<script setup>
import { ref, reactive, computed } from 'vue'
import WordGuess from './WordGuess.vue'
const words = reactive([
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
])

function scrambleWords() {
  const num = Math.floor(Math.random() * words.length)

  let correctWord = words[num]
  let word = computed(() => {
    return ref(
      words[num]
        .split('')
        .sort(() => 0.5 - Math.random())
        .join(''),
    )
  })
  console.log(word.value)
}
scrambleWords()
</script>

<style scoped></style>
