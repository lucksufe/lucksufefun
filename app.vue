<template>
  <div>
    <NuxtPage />
  </div>
</template>

<script setup lang="ts">
useHead({
  title: '图标导航',
  meta: [
    { name: 'description', content: '图标导航' }
  ],
  bodyAttrs: {
    class: '导航'
  },
  script: [ { innerHTML: 'console.log(\'百亿补贴\')' } ]
})
useSeoMeta({
  title: '图标导航',
  ogTitle: '图标导航',
  description: '简单的图标导航',
  ogDescription: '磁贴样式的APP图标',
  ogImage: 'https://pdd.lucksufe.fun/favicon.ico',
})
</script>