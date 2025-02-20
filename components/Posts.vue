<script setup lang="ts">
import { ref } from 'vue'

interface Post {
  id: number;
  title: string;
}

const data = ref<Post[]>([])

async function fetchData() {
  data = await fetch("https://jsonplaceholder.typicode.com/posts").then(res => res.json())
}
</script>

<template>
  <div>
    <button @click="fetchData">Load Posts</button>
    <ul>
      <li v-for="post in data" :key="post.id">{{ post.title }}</li> 
    </ul>
  </div>
</template>
