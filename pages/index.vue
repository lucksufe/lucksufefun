<template>	
	<div class="index">
		<IndexApp v-for="(app, i) in app_list" :idx="i" :appData="app"></IndexApp>
	</div>	
</template>
<script setup lang="ts">
import app_list from '../config/applications.json'
</script>
<style>
.index {
	display: -webkit-flex;
    display: flex;
    flex-direction: row;  
    flex-wrap: wrap;
}
</style>