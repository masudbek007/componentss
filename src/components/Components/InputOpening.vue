<template>
    <div id="app" class="relative h-screen">
     
      <div v-if="overlayVisible" class="fixed inset-0 bg-black bg-opacity-50 z-10"></div>
      <div class="flex justify-center h-full">
        <div class="absolute">
            <div>
                <input
                type="text"
                v-model="inputValue"
                @focus="showOverlay"
                @blur="hideOverlay"
                placeholder="Qidirmoq ..."
                class="pr-20 pl-7 py-2 outline-none text-lg mt-10 border hover:border-sky-500 rounded relative z-20"/>
            </div>
          </div>
          
        </div>
      </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const inputValue = ref('');
  const overlayVisible = ref(false);
  
  function showOverlay() {
    overlayVisible.value = true;
  }
  
  function hideOverlay() {
    setTimeout(() => {
      overlayVisible.value = false;
    }, 100); 
  }
  </script>
  
  <style scoped>
  </style>
  