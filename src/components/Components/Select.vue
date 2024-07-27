<template>
  <div class="ml-9 mt-10 mb-4 overflow-hidden">
    <div 
      class="flex justify-between rounded-2xl items-center max-w-[350px] p-4 bg-gray-100 cursor-pointer" 
      @click="toggleContent"
    >
      <div class="flex items-center">
        <span class="font-bold">{{ title }}</span>
      </div>
      <span class="text-gray-600">{{ count }} ta reklama</span>
      <button class="bg-none border-none text-lg">
        <i :class="['fas', 'fa-chevron-up', { rotate: isOpen }]"></i>
      </button>
    </div>
    <div v-if="isOpen" class="p-4 grid grid-cols-3">
      <div class="py-4" v-for="(sub, index) in subcategories" :key="index">{{ sub }}</div>
    </div>
  </div>
</template>

<script setup>
import { ref, defineProps } from 'vue';

const props = defineProps({
  title: {
    type: String,
    required: true
  },
  count: {
    type: Number,
    required: true
  },
  subcategories: {
    type: Array,
    required: true
  }
});

const isOpen = ref(false);

const toggleContent = () => {
  isOpen.value = !isOpen.value;
};
</script>

<style scoped>
button i {
  transition: transform 0.3s ease;
}

button i.rotate {
  transform: rotate(180deg);
}
</style>
