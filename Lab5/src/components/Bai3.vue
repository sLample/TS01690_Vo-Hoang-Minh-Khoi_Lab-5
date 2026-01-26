<template>
  <div class="col-sm-8 p-4">
    <h1>Thông tin cá nhân</h1>

    <form>
      <div class="mb-3">
        <label>Họ và Tên:</label>
        <input v-model="userInfo.name" class="form-control" />
      </div>

      <div class="mb-3">
        <label>Tuổi:</label>
        <input v-model="userInfo.age" type="number" class="form-control" />
      </div>

      <div class="mb-3">
        <label>Email:</label>
        <input v-model="userInfo.email" type="email" class="form-control" />
      </div>
    </form>

    <div class="mt-4 p-3 bg-dark text-white rounded">
      <h3>Thông tin đã nhập:</h3>
      <p><b>Họ tên:</b> {{ userInfo.name }}</p>
      <p><b>Tuổi:</b> {{ userInfo.age }}</p>
      <p><b>Email:</b> {{ userInfo.email }}</p>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue'

const userInfo = reactive({
  name: '',
  age: '',
  email: ''
})
</script>
