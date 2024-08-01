<template>
    <div>
      <div>
        <button @click="showModal = true" class="bg-sky-500 px-5 py-2">Open Modal</button>
      </div>
      <div v-if="showModal" class="modal">
        <div class="modal-content">
          <button @click="showModal = false" class="close-btn">Close</button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const showModal = ref(false);
  </script>
  
  <style>
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .modal-content {
    background-color: white;
    padding: 20px;
    border-radius: 8px;
  }
  
  .close-btn {
    background-color: red;
    color: white;
    padding: 5px 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  </style>
  