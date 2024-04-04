<script setup lang="ts">
import { ref } from 'vue'
import CheckedInput from './components/CheckedInput.vue'

// component specific debug section

// checked input updatable expected value testing variable
const variableExpectedValue = ref<String>('');


// general debugging utils

function logToAlert(event: Event): void {
  alert('yipee')
}

</script>

<template>
  <p>What should we expect?</p>
  <input v-model="variableExpectedValue">

  <checked-input v-bind:expectedInput="variableExpectedValue" @correctAnswerPassed="logToAlert" />
</template>

<style scoped>
input {
  font-size: 20px;
}
</style>
