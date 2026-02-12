<template>
  <div>
    <NuxtPage />
  </div>
</template>

<script setup lang="ts">
useHead({
  title: '工具箱',
  meta: [
    { name: 'description', content: '工具箱' }
  ],
  bodyAttrs: {
    class: '导航'
  }
})
useSeoMeta({
  title: '工具箱',
  ogTitle: '图标导航',
  description: '简单的图标导航',
  ogDescription: '磁贴样式的APP图标',
  ogImage: 'https://pdd.lucksufe.fun/favicon.ico',
})
</script>
