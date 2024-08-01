<template>
  <div class="ml-10 mt-5">
    <div class="relative">
      <div
        class="mx-3 border px-4 outline-none hover:shadow-md shadow-sky-500 hover:text-sky-500 border-spacing-1"
        @click="toggleDropdown"
      >
        <div class="p-2">
          {{ selectedOptionText || 'Select an option' }}
        </div>
      </div>
      <div v-if="dropdownOpen" class="absolute bg-white border mt-1 w-full shadow-lg">
        <div
          v-for="option in options"
          :key="option.value"
          class="cursor-pointer p-2 hover:bg-sky-100"
          @click="selectOption(option)"
        >
          {{ option.text }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const options = [
  { value: 'option1', text: 'Option 1' },
  { value: 'option2', text: 'Option 2' },
  { value: 'option3', text: 'Option 3' }
];

const selectedOptionText = ref('');
const dropdownOpen = ref(false);

const selectOption = (option) => {
  const newOptionText = option.text;
  if (!selectedOptionText.value.includes(newOptionText)) {
    selectedOptionText.value += (selectedOptionText.value ? ', ' : '') + newOptionText;
  }
  dropdownOpen.value = false;
};

const toggleDropdown = () => {
  dropdownOpen.value = !dropdownOpen.value;
};
</script>

<style scoped>
.cursor-pointer {
  cursor: pointer;
}
.hover:bg-sky-100:hover {
  background-color: #e0f7ff;
}
.relative {
  position: relative;
}
.absolute {
  position: absolute;
  z-index: 10;
}
.bg-white {
  background-color: #ffffff;
}
</style>
