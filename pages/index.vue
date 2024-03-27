<template>	
	<div ref="container">
		<div id="nav-container">			
			<IndexApp v-for="(app, i) in app_list" :idx="i" :appData="app"></IndexApp>
		</div>
	</div>
</template>
<script setup lang="ts">
import app_list from '../config/applications.json'
</script>
<style></style>