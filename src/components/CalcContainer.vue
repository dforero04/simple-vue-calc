<script setup>
  import {ref} from 'vue';

  const equation = ref('');
</script>

<template>
  <input v-model="equation" placeholder="Enter calculation">
</template>
