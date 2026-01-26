<template>
  <div class="create-post">
    <h2>Tạo bài viết</h2>

    <input v-model="post.title" placeholder="Tiêu đề" />
    <input v-model="post.author" placeholder="Tác giả" />
    <textarea v-model="post.content" placeholder="Nội dung"></textarea>

    <button @click="addPost">Đăng bài</button>
  </div>
</template>

<script setup>
import { reactive } from 'vue'

const emit = defineEmits(['add-post'])

const post = reactive({
  title: '',
  author: '',
  content: ''
})

const addPost = () => {
  emit('add-post', { ...post })
  post.title = ''
  post.author = ''
  post.content = ''
}
</script>

<style scoped>
.create-post {
  max-width: 500px;
  margin: 0 auto 40px;
  padding: 20px;
  background: #1e1e1e;
  border-radius: 10px;
}

h2 {
  text-align: center;
  margin-bottom: 15px;
}

input,
textarea {
  width: 100%;
  margin-bottom: 12px;
  padding: 10px;
  border-radius: 6px;
  border: none;
  background: #2c2c2c;
  color: #fff;
}

textarea {
  resize: none;
  height: 90px;
}

button {
  width: 100%;
  padding: 10px;
  background: #0dcaf0;
  border: none;
  border-radius: 6px;
  font-weight: bold;
  cursor: pointer;
}
</style>
