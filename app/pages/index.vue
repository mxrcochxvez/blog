<template>
  <main class="home-container">
    <h1>Marco's Blog</h1>
    
    <ul>
      <li v-for="{ path, title } in blogPosts">
        <NuxtLink :to="path">
          {{ title }}
        </NuxtLink>
      </li>
    </ul>
  </main>
</template>

<script setup lang="ts">
  const { data: blogPosts } = await useAsyncData('posts', () => queryCollection('blog').all());
</script>