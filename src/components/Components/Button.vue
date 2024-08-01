<template>
    <button :disabled="isLoading" @click="handleClick">
      <span v-if="isLoading">yuklanmoqda ...</span>
      <span v-else>bosing</span>
    </button>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const isLoading = ref(false);
  
  const handleClick = async () => {
    isLoading.value = true;
    await new Promise(resolve => setTimeout(resolve, 3000));
    isLoading.value = false;
  };
  </script>
  
  
  