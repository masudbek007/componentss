<template>
  <div>
    <label for="options">Tanlang:</label>
    <select id="options" v-model="selectedOptions" multiple>
      <option v-for="option in options" :key="option.value" :value="option.value">
        {{ option.text }}
      </option>
    </select>
    <p>Tanlangan variantlar: {{ selectedOptions }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const options = [
  { value: 'option1', text: 'Option 1' },
  { value: 'option2', text: 'Option 2' },
  { value: 'option3', text: 'Option 3' }
];

const selectedOptions = ref([]);
</script>

<style scoped>
</style>
