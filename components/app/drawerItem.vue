<script setup>
defineProps({
    item: {
        type: Object,
        required: true
    }
})
</script>

<template>
    <NuxtLink class="drawerItem" :to="item.path">
        <h2 v-text="item.text">
        </h2>
        <component :is="item.icon"></component>
    </NuxtLink>
</template>

<style lang="scss" scoped>
.drawerItem {
    @apply bg-white text-primary rounded-lg py-2 px-4 flex items-center justify-between;
}
</style>