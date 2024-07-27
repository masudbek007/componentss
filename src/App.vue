<template>
  <div>
    <div>
      <Select
        title="Erkaklar kiyimi"
        :count="11"
        :subcategories="[
          'Aksessuarlar',
          'Kiyim to\'plamlari',
          'Uy va uxlash uchun',
          'Jumperlar, futbolkalar',
          'Shimlar, shimlar',
          'Ustki kiyim',
          'Oyoq kiyimlari',
        ]"
      />
    </div>
    <div class="password-input-container">
      <input
        :type="passwordFieldType"
        class="ml-10 pl-2 outline-none rounded-lg shadow shadow-sky-500 pr-20 py-2 border border-spacing-1 hover:border border-sky-500"
        placeholder="Parolni kiriting"
      />
      <span @click="togglePasswordVisibility" class="eye-icon">
        <i :class="passwordFieldType === 'password' ? 'fa fa-eye' : 'fa fa-eye-slash'"></i>
      </span>
    </div>
     
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Select from './components/Components/Select.vue';

const passwordFieldType = ref('password');
const togglePasswordVisibility = () => {
  passwordFieldType.value =
    passwordFieldType.value === 'password' ? 'text' : 'password';
};

const options = ref([
  { value: 'option1', text: 'Option 1' },
  { value: 'option2', text: 'Option 2' },
  { value: 'option3', text: 'Option 3' }
]);

const selectedOptions = ref([]);
</script>

<style scoped>
.password-input-container {
  position: relative;
  display: inline-block;
}

.eye-icon {
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
}
</style>

<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css"
/>
