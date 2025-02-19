<template>
  <div class="">
    <WordGuess :scrambled="word" :correct="correctWord" @scramble="scrambleWords()" />
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import WordGuess from './WordGuess.vue'

const words = reactive([
  "brick", "frost", "blunt", "grasp", "cling", "drift", "plumb", "swift", "charm", "trunk",
  "brisk", "flint", "crisp", "glint", "stomp", "clamp", "prong", "twist", "clump", "brunt",
  "thump", "crank", "stint", "whisk", "plank", "stark", "crush", "grump", "plush", "draft",
  "throb", "flask", "stung", "grunt", "blitz", "swamp", "twang", "scalp", "whiff", "crush",
  "brass", "swoop", "quilt", "prism", "drank", "scorn", "tramp", "spunk", "snarl", "flick",
  "grind", "pluck", "throb", "crisp", "sworn", "broth", "stoke", "clash", "swank", "clout",
  "whack", "brawn", "frisk", "chomp", "slink", "swish", "spool", "drown", "whisk", "splat",
  "gruff", "tryst", "swoon", "chasm", "brute", "churn", "frank", "chomp", "sworn", "brash",
  "glove", "thump", "graft", "drill", "slink", "clink", "prone", "brisk", "spine", "trill",
  "plump", "frost", "flair", "stark", "broil", "skimp", "shorn", "whirl", "chunk", "grill"
]);
let word = ref('')
let correctWord = ref('')
function scrambleWords() {
  
  const num = Math.floor(Math.random() * words.length)

  correctWord = words[num]

  word.value = words[num]
    .split('')
    .sort(() => 0.5 - Math.random())
    .join('')
  while (correctWord == word.value){
    word.value = words[num]
    .split('')
    .sort(() => 0.5 - Math.random())
    .join('')
  }

  words.splice(num,1)
}
scrambleWords()
</script>

<style scoped></style>
