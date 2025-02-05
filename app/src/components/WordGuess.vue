<template>
  <div>
    <form action="" method="get" class="" @submit.prevent="submit">
      <input placeholder="Type here" class="input input-bordered w-full max-w-xs" v-model="guess" />
    </form>
    <h2 class="text-xl" v-if="win == true">{{ word }}</h2>
    <h3>{{ win_counter }}</h3>
    <WordScramble />
  </div>
</template>

<script setup>
import { ref } from 'vue'
const props = defineProps({
  scrambled: String,
  correct: String,
  word_list: Array,
  word_next: Function,
})

const guess = ref('')
let win
let win_counter = ref(0)
const submit = () => {
  if (props.correct === guess.value) {
    console.log('yipee')
    win = true
    win_counter.value++
    console.log(win_counter.value)
  }
}
</script>

<style scoped></style>
