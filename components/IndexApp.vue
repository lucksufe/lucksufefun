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
    display: flex;
    flex-direction: row;  
    flex-wrap: wrap;
    position: relative;
    align-items: center;
    justify-content: center;
    /* background-color: #fefaea; */
    border-radius: 1rem;
    padding: 10px; 
    margin: 10px;
    border-color: #ffcc00;
    border-width: 1px;
    border-style: solid;
    width: 150px;
    height: 150px;
    background-image: linear-gradient(135deg, rgb(216, 178, 8), rgb(254, 250, 234) 55% 90%, rgb(236, 178, 16) 100%);
}
.index-app img {
    position: absolute;
    top: 35px;
    left: 35px;
    width: 100px;
    height: 100px;
    transition: transform 0.5s ease-in-out;
}   
.index-app:hover img {
    transform: scale(1.15);
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