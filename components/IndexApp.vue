<template>
    <a
        class="index-app"
        :href="appData.url"
        target="_blank"
        rel="noopener noreferrer"
        :title="appData.description || appData.title"
        :aria-label="appData.title"
    >
        <img :src="appData.icon" :alt="appData.title" loading="lazy" decoding="async" />
        <p class="title">{{appData.title}}</p>
    </a>
</template>

<script setup lang="ts"> 
defineProps<{
    appData: {
        title: string
        url: string
        icon: string
        description?: string
        type?: string
        is_show?: boolean
    }
}>()
</script>

<style scoped>
.index-app {
    display: flex;
    flex-direction: column;
    gap: 10px;
    align-items: center;
    justify-content: center;
    border-radius: 16px;
    padding: 14px;
    width: 160px;
    height: 160px;
    text-decoration: none;
    color: inherit;
    background: rgba(255, 255, 255, 0.08);
    -webkit-backdrop-filter: blur(14px) saturate(140%);
    backdrop-filter: blur(14px) saturate(140%);
    border: 1px solid rgba(255, 255, 255, 0.18);
    box-shadow:
        0 18px 40px rgba(0, 0, 0, 0.35),
        inset 0 1px 0 rgba(255, 255, 255, 0.10);
    transition: transform 180ms ease, box-shadow 180ms ease;
}
.index-app img {
    width: 72px;
    height: 72px;
    object-fit: contain;
    filter: drop-shadow(0 10px 16px rgba(0, 0, 0, 0.35));
    transition: transform 180ms ease;
}   
.index-app:hover {
    transform: translateY(-3px);
    box-shadow:
        0 24px 54px rgba(0, 0, 0, 0.48),
        inset 0 1px 0 rgba(255, 255, 255, 0.12);
}
.index-app:hover img {
    transform: scale(1.06);
}
.index-app:active {
    transform: translateY(-1px);
}
.index-app:focus-visible {
    outline: 2px solid rgba(255, 255, 255, 0.85);
    outline-offset: 4px;
}
.title {
    margin: 0;
    width: 100%;
    text-align: center;
    color: rgba(255, 255, 255, 0.88);
    font-size: 14px;
    font-weight: 600;
    line-height: 1.2;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    overflow: hidden;
}
@media (prefers-color-scheme: light) {
    .index-app {
        background: rgba(255, 255, 255, 0.58);
        border: 1px solid rgba(0, 0, 0, 0.08);
        box-shadow:
            0 16px 38px rgba(0, 0, 0, 0.10),
            inset 0 1px 0 rgba(255, 255, 255, 0.65);
    }
    .index-app:hover {
        box-shadow:
            0 22px 54px rgba(0, 0, 0, 0.16),
            inset 0 1px 0 rgba(255, 255, 255, 0.72);
    }
    .index-app:focus-visible {
        outline: 2px solid rgba(0, 0, 0, 0.75);
    }
    .title {
        color: rgba(10, 10, 12, 0.80);
    }
}
</style>
