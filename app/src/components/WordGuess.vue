<template>
  <div class="">
    <div class="flex justify-center">
      <form action="" method="get" class="" @submit.prevent="submit">
        <input
          placeholder="Type here"
          class="input input-bordered w-full max-w-xs"
          v-model="guess"
        />
      </form>
    </div>

    <div class="grid justify-center grid-rows-2">
      <h2 class="text-xl">scrambled Word: {{ scrambled }}</h2>
      <br />
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
    console.log('yipee')
    emit('scramble')
    win_counter.value++
    guess.value = ''
  }
}
</script>

<style scoped></style>
