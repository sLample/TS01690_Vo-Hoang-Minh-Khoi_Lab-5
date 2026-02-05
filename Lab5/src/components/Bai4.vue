<template>
  <div class="container py-5">
    <!-- HEADER -->
    <div class="text-center mb-5">
      <h1 class="fw-bold">📝 Blog Mini</h1>
    </div>

    <div class="row g-4 align-items-start">
      <!-- CREATE POST -->
      <div class="col-12 col-lg-4">
        <div class="card shadow-sm border-0">
          <div class="card-body">
            <h5 class="card-title mb-3">✍️ Tạo bài viết</h5>
            <CreatePost @add-post="addPost" />
          </div>
        </div>
      </div>

      <!-- POST LIST -->
      <div class="col-12 col-lg-8">
        <div class="card shadow-sm border-0">
          <div class="card-body">
            <h5 class="card-title mb-3">📚 Danh sách bài viết</h5>
            <PostList :posts="posts" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import CreatePost from './CreatePost.vue'
import PostList from './PostList.vue'

const posts = ref([
  {
    title: 'Bật Mí 8 Nguyên Tắc Phối Màu Quần Áo Sành Điệu',
    author: 'Nguyễn Văn Tèo',
    content: 'Bạn có thể phối áo màu xanh lá, quần màu kem và giày màu tím...',
    backgroundColor: '#f8f9fa',
    textColor: '#212529'
  }
])

function addPost(newPost) {
  posts.value.unshift(newPost)
}
</script>

<style scoped>
.container {
  max-width: 1200px;
}

.card-title {
  font-weight: 600;
}

@media (max-width: 992px) {
  h1 {
    font-size: 1.8rem;
  }
}
</style>
