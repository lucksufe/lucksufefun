<template>
    <div class="index-app" v-show="appData.is_show" :title="appData.description">        
        <a :href="appData.url" target="_blank">
            <img :src="appData.icon"/>
        </a>
        <p>{{appData.title}}</p>
    </div>
</template>

<!-- 动态加载了appData的数据，没有的话上面的appData.title会报错，因为没有appData -->
<script setup lang="ts"> 
const props = defineProps<{
	appData: any,
	idx: number
}>()
</script>

<style scoped>
.index-app {
    display: -webkit-flex;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #fefaea;
    border-radius: 1rem;
    padding: 10px; 
    border-color: #f4eed6;
    border-width: 1px;
    border-style: solid;
    width: 150px;
    height: 150px;
    flex-direction: row;  
    flex-wrap: wrap  
}
.index-app img {
    background-color: #eee;
    position: absolute;
    top: 35px;
    left: 35px;
    width: 100px;
    height: 100px;
}   
p {
    width: 100%;
    text-align: center;
    position: absolute;
    top: 125px;
    color     : #333;
    font-size : 16px;
}
</style>