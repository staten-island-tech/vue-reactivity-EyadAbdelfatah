<template>
  <div class="">
    <div class="flex justify-center">
      <form action="" method="get" class="" @submit.prevent="submit">
      <input placeholder="Type here" class="input input-bordered w-full max-w-xs" v-model="guess" />
    </form>
    </div>
    
    <div class="grid grid-cols-7 gap-4">
    <button class="btn btn-default">Animals</button>
    <button class="btn btn-default">Fruits</button>
    <button class="btn btn-default">Countries</button>
    <button class="btn btn-default">Sports</button>
    <button class="btn btn-default">Colors</button>
    <button class="btn btn-default">Occupations</button>
    <button class="btn btn-default">Technology</button>
    </div>
    
    <div class="flex justify-center">
      <h2 class="text-xl">scrambled Word: {{ scrambled }}</h2>
    <h3>Win Counter: {{ win_counter }}</h3>
    <WordScramble />
    </div>
    
  </div>
</template>

<script setup>
import { ref, defineEmits } from 'vue'
const props = defineProps({
  scrambled: String,
  correct: String,
})

const guess = ref('')
const emit = defineEmits('')
let win_counter = ref(0)
const submit = () => {
  if (props.correct == guess.value) {
    emit('scramble')
    win_counter.value++
    guess.value = ''
  } 
}
</script>

<style scoped></style>
