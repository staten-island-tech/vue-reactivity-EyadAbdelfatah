<template>
  <div>
    <form action="" method="get" class="" @submit.prevent="submit">
      <input placeholder="Type here" class="input input-bordered w-full max-w-xs" v-model="guess" />
      <button class="btn">Default</button>
    </form>
    <WordScramble />
    <h2 class="text-white">{{ guess }}</h2>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import WordScramble from './WordScramble.vue'

const guess = ref('')

const x = ref('')
const submit = () => {
  console.log('submit is accessed')
  console.log(x)
  if (guess.value == correct) {
    console.log('u right')
  } else {
    console.log('u suck')
  }
}
</script>

<style scoped></style>
