<template>	
	<div class="index">
		<IndexApp v-for="app in visibleApps" :key="app.url || app.title" :appData="app"></IndexApp>
	</div>	
</template>
<script setup lang="ts">
import app_list from '../config/applications.json'
const visibleApps = computed(() => app_list.filter((app) => app.is_show !== false))
</script>
<style>
.index {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 18px;
    padding: 28px;
    max-width: 1100px;
    margin: 0 auto;
	justify-items: center;
    align-content: start;
}
*,
*::before,
*::after {
    box-sizing: border-box;
}
body {
    margin: 0;
    min-height: 100vh;
    font-family: system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji";
    color: rgba(255, 255, 255, 0.92);
    background:
        radial-gradient(900px 700px at 10% 10%, rgba(255, 255, 255, 0.10), transparent 60%),
        radial-gradient(700px 700px at 90% 25%, rgba(255, 255, 255, 0.06), transparent 55%),
        radial-gradient(900px 700px at 50% 90%, rgba(255, 255, 255, 0.05), transparent 60%),
        linear-gradient(180deg, #0b0d12 0%, #07080b 100%);
}
@supports (background: color-mix(in srgb, white 50%, black)) {
    body {
        background:
            radial-gradient(900px 700px at 10% 10%, color-mix(in srgb, #fff 12%, transparent), transparent 60%),
            radial-gradient(700px 700px at 90% 25%, color-mix(in srgb, #fff 8%, transparent), transparent 55%),
            radial-gradient(900px 700px at 50% 90%, color-mix(in srgb, #fff 7%, transparent), transparent 60%),
            linear-gradient(180deg, #0b0d12 0%, #07080b 100%);
    }
}
@media (prefers-color-scheme: light) {
    body {
        color: rgba(10, 10, 12, 0.88);
        background:
            radial-gradient(900px 700px at 10% 10%, rgba(0, 0, 0, 0.06), transparent 60%),
            radial-gradient(700px 700px at 90% 25%, rgba(0, 0, 0, 0.04), transparent 55%),
            radial-gradient(900px 700px at 50% 90%, rgba(0, 0, 0, 0.03), transparent 60%),
            linear-gradient(180deg, #ffffff 0%, #f3f4f6 100%);
    }
}
</style>
