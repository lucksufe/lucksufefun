<template>
    <div class="index-app" v-show="appData.is_show" :title="appData.description">        
        <a :href="appData.url" target="_blank">
            <img :src="appData.icon" height="64" width="64"/>
        </a>
        {{appData.title}}
    </div>
</template>

<!-- 动态加载了appData的数据，没有的话上面的appData.title会报错，因为没有appData -->
<script setup lang="ts"> 
const props = defineProps<{
	appData: any,
	idx: number
}>()
</script>