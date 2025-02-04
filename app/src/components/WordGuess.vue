<template>
  <div>
    
    <form action="" method="get" class="text-white" @submit.prevent="submit">

      <input   placeholder="Type here" class="input input-bordered w-full max-w-xs" v-model="guess"/>
    
    </form>
    <WordScramble/>


  </div>
</template>

<script setup >

import {ref} from 'vue'
const props = defineProps({
  scrambled:String,
  correct:String,
})

const guess = ref('')


const submit = () =>{

  if (props.correct === guess.value){

  }
}

</script>

<style scoped></style>
