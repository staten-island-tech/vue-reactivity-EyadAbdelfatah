<template>
  <div>
    <form action="" method="get" class="" @submit.prevent="submit">
      <input placeholder="Type here" class="input input-bordered w-full max-w-xs" v-model="guess" />
    </form>
    <h2 class="text-xl">{{ scrambled }}</h2>
    <h3>{{ win_counter }}</h3>
    <WordScramble />
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
let win
let win_counter = ref(0)
const submit = () => {
  if (props.correct == guess.value) {
    console.log(1)
    emit('scramble')
    win = true
    win_counter.value++
  } else {
    console.log('no yipee')
  }
  console.log(props.scrambled)
}
</script>

<style scoped></style>
