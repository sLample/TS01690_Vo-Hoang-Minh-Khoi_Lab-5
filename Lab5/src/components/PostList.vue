<template>
  <div class="post-list">
    <h2>Danh sách bài viết</h2>

    <div v-for="(post, index) in posts" :key="index" class="post-card">
      <h3>{{ post.title }}</h3>
      <p class="author">Tác giả: {{ post.author }}</p>
      <p>{{ post.content }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  posts: Array
})
</script>

<style scoped>
.post-list {
  max-width: 700px;
  margin: 0 auto;
}

h2 {
  text-align: center;
  margin-bottom: 20px;
}

.post-card {
  background: #d9f5f9;
  color: #000;
  padding: 20px;
  border-radius: 8px;
  margin-bottom: 20px;
  text-align: center;
}

.author {
  font-style: italic;
  margin: 8px 0;
}
</style>
