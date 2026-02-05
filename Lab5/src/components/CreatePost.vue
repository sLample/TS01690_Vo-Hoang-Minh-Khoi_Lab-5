<template>
  <div class="create-post">
    <h2>Tạo bài viết</h2>

    <input v-model="post.title" placeholder="Tiêu đề" />
    <input v-model="post.author" placeholder="Tác giả" />
    <textarea v-model="post.content" placeholder="Nội dung"></textarea>

    <p v-if="error" class="error">{{ error }}</p>

    <button @click="submitPost">Đăng bài</button>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'

const emit = defineEmits(['add-post'])

const post = reactive({
  title: '',
  author: '',
  content: ''
})

const error = ref('')

const submitPost = () => {
  if (!post.title || !post.author || !post.content) {
    error.value = 'Vui lòng nhập đầy đủ thông tin'
    return
  }

  emit('add-post', { ...post, id: Date.now() })

  post.title = ''
  post.author = ''
  post.content = ''
  error.value = ''
}
</script>

<style scoped>
.create-post {
  width: 100%;
  padding: 30px;
  background: linear-gradient(180deg, #1f1f1f, #2a2a2a);
  border-radius: 14px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.6);
}

h2 {
  text-align: center;
  margin-bottom: 20px;
  color: #ffffff;
}

input,
textarea {
  width: 100%;
  padding: 12px;
  margin-bottom: 14px;
  border-radius: 8px;
  border: none;
  background: #ffffff;
  color: #000000;
  font-size: 15px;
}

input::placeholder,
textarea::placeholder {
  color: #666;
}

textarea {
  resize: none;
  height: 120px;
}

button {
  width: 100%;
  padding: 12px;
  background: #0dcaf0;
  border: none;
  border-radius: 8px;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  color: #000;
  transition: background 0.2s;
}

button:hover {
  background: #31d2f2;
}

.error {
  color: #ff6b6b;
  text-align: center;
  margin-bottom: 10px;
}
</style>
