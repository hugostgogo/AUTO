<script setup>
defineProps({
    item: {
        type: Object,
        required: true
    }
})
</script>
    
<template>
    <NuxtLink :to="item.path" class="menuItem">
        <h2 v-text="item.text"></h2>
        <component :is="item.icon"></component>
    </NuxtLink>
</template>
    
<style lang="scss" scoped>
    .menuItem {
        @apply flex justify-between items-center px-4 py-2 transition-all duration-300;

        &:hover {
            @apply
                bg-gray-100
            ;
        }
    }
</style>