<template>
  <div class="">
    <SelectCategory />
    <WordGuess :scrambled="word" :correct="correctWord" @scramble="scrambleWords()" />
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import WordGuess from './WordGuess.vue'
import SelectCategory from './SelectCategory.vue'
const words = reactive([
  'acorn',
  'book',
  'cloud',
  'drum',
  'eagle',
  'feather',
  'giraffe',
  'hippopotamus',
  'ice',
  'jewel',
  'kangaroo',
  'leopard',
  'moose',
  'notebook',
  'owl',
  'penguin',
  'quiver',
  'rocket',
  'snowflake',
  'tiger',
  'unicorn',
  'vulture',
  'whistle',
  'xenon',
  'oganesson',
  'yak',
  'zinc',
  'apricot',
  'brush',
  'cactus',
  'dog',
  'elephant',
  'flower',
  'glove',
  'hippopotamus',
  'insect',
  'jar',
  'kiwi',
  'lemon',
  'mango',
  'net',
  'octopus',
  'parrot',
  'quilt',
  'rainbow',
  'scorpion',
  'tree',
  'umbrella',
  'violet',
  'whalen',
  'yellow',
  'zebra',
  'apple',
  'ball',
  'chair',
  'crayon',
  'dinosaur',
  'elephant',
  'goose',
  'hatch',
  'iron',
  'jacket',
  'kite',
  'magnet',
  'nail',
  'orange',
  'piano',
  'quiz',
  'reindeer',
  'snow',
  'trolley',
  'upward',
  'vortex',
  'wrench',
  'x-ray',
  'yoga',
  'zoo',
  'art',
  'blue',
  'cat',
  'doghouse',
  'elephant',
  'fridge',
  'guitar',
  'hermit',
  'island',
  'jungle',
  'kitten',
  'lemur',
  'noodle',
])
let word = ref('')
let correctWord = ref('')
function scrambleWords() {
  const num = Math.floor(Math.random() * words.length)

  correctWord = words[num]

  word.value = words[num]
    .split('')
    .sort(() => 0.5 - Math.random())
    .join('')
}
scrambleWords()
</script>

<style scoped></style>
