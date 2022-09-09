<script setup>
defineProps({
    title: {
        type: String,
        required: false
    }
})
</script>
    
<template>
    <div class="page">
        <h2 v-if="title" v-text="title" class="title"></h2>
        <slot />
    </div>
</template>
    
<style lang="scss" scoped>
.page {
    @apply p-4 flex flex-col;
}

.title {
    @apply font-bold text-xl text-primary;
}
</style>
      