<template>
  <div class="post-list">
    <h2>Danh sách bài viết</h2>

    <div
      v-for="(post, index) in posts"
      :key="post.id"
      class="post-card"
      :class="{ even: index % 2 === 0 }"
      :style="cardStyle"
    >
      <h3 class="title">{{ post.title }}</h3>
      <p class="author">{{ post.author }}</p>
      <p class="content">{{ post.content }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  posts: Array
})

const cardStyle = {
  border: '1px solid #ddd',
  backgroundColor: '#fff'
}
</script>

<style scoped>
.post-list {
  max-width: 900px;
  margin: 0 auto;
}

.post-card {
  padding: 20px;
  border-radius: 8px;
  margin-bottom: 20px;
}

.title {
  color: #198754;
  font-size: 22px;
  margin-bottom: 10px;
}

.author {
  color: #dc3545;
  font-weight: bold;
  margin-bottom: 10px;
}

.content {
  color: #333;
  line-height: 1.6;
}

.even {
  box-shadow: 0 0 6px rgba(0, 0, 0, 0.1);
}
</style>
