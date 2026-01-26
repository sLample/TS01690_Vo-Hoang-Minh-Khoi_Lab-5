<template>
  <div class="p-4">
    <input
      v-model="userInput"
      placeholder="Nhập dữ liệu vào đây"
      class="form-control"
    />
    <p class="mt-2">Giá trị bạn nhập: {{ userInput }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const userInput = ref('FPL')
</script>
