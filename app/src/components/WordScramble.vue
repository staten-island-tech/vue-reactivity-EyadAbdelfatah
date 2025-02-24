<template>
  <div class="">
    <SelectCategory />
    <WordGuess :scrambled="word" :correct="correctWord" @scramble="scrambleWords()" />
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import WordGuess from './WordGuess.vue'

const words = reactive([
  'apple',
  'banana',
  'cherry',
  'dog',
  'elephant',
  'forest',
  'guitar',
  'house',
  'island',
  'jungle',
  'kangaroo',
  'lemon',
  'mountain',
  'notebook',
  'ocean',
  'pencil',
  'quartz',
  'river',
  'sunset',
  'tiger',
  'umbrella',
  'volcano',
  'whisper',
  'xylophone',
  'yogurt',
  'zebra',
  'anchor',
  'bridge',
  'castle',
  'diamond',
  'engine',
  'fountain',
  'glacier',
  'harbor',
  'icicle',
  'jigsaw',
  'knight',
  'lantern',
  'meadow',
  'nectar',
  'orchid',
  'penguin',
  'quiver',
  'rainbow',
  'sapphire',
  'tornado',
  'unicorn',
  'voyage',
  'waterfall',
  'xenon',
  'yacht',
  'zeppelin',
  'asteroid',
  'blossom',
  'compass',
  'dragonfly',
  'emerald',
  'firefly',
  'galaxy',
  'horizon',
  'illusion',
  'jasmine',
  'koala',
  'labyrinth',
  'mermaid',
  'nebula',
  'octopus',
  'paradise',
  'quokka',
  'raven',
  'starlight',
  'treasure',
  'utopia',
  'vortex',
  'wildflower',
  'x-ray',
  'yonder',
  'zephyr',
  'alchemy',
  'breeze',
  'crystal',
  'destiny',
  'echo',
  'feather',
  'gargoyle',
  'hummingbird',
  'infinity',
  'journey',
  'kaleidoscope',
  'lullaby',
  'mystery',
  'nirvana',
  'obsidian',
  'phoenix',
  'quest',
  'radiance',
  'serenity',
  'twilight',
  'unravel',
  'vivid',
  'wanderlust',
  'xenophile',
  'yearning',
  'zenith',
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
  while (correctWord == word.value) {
    word.value = words[num]
      .split('')
      .sort(() => 0.5 - Math.random())
      .join('')
  }

  words.splice(num, 1)
}
scrambleWords()
</script>

<style scoped></style>
