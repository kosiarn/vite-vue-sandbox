<script setup lang="ts">

import { ref, computed, watch } from 'vue'

const props = defineProps(['expectedInput']);
const currentInput = ref<String>('');
const emit = defineEmits(['correct-answer-passed'])

// Input checker handling

const isCorrectAnswer = computed(() => {
  return currentInput.value === props.expectedInput;
})

watch(isCorrectAnswer, (isCorrectAnswer) => {
  if(isCorrectAnswer){
    emit('correct-answer-passed')
  }
})

</script>

<template>
  <input v-model="currentInput" v-bind:disabled="isCorrectAnswer" /> 
</template>

<style scoped>
/* TODO: make a proper stylesheet or do Tailwind */
input {
  font-size: 20px;
  background-color: #8a7272;
}
</style>
