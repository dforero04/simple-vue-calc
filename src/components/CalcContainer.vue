<script setup>
import CalcKeypad from './CalcKeypad.vue'
import { reactive } from 'vue'

const equation = reactive({
  equation: ''
})
</script>

<template>
  <input v-model="equation" placeholder="Enter calculation" />
  <CalcKeypad/>
</template>
