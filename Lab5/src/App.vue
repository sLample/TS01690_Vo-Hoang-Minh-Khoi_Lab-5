<template>
  <div class="container">
    <CreatePost @add-post="addPost" />
    <PostList :posts="posts" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import CreatePost from './components/CreatePost.vue'
import PostList from './components/PostList.vue'

const posts = ref([])

const addPost = (post) => {
  posts.value.push(post)
}
</script>

<style scoped>
.container {
  min-height: 100vh;
  padding: 40px 16px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 40px;

  background: #1c1c1c;
  color: #fff;
}
</style>
