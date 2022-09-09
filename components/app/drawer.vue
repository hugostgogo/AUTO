<script setup>
import Home from 'vue-material-design-icons/Home.vue'
import { onClickOutside } from '@vueuse/core'

const drawerRef = ref(null);

onClickOutside(drawerRef, (e) => Drawer.close())


const Drawer = reactive({
    state: false,
    items: [
        {
            text: 'Hom',
            icon: Home,
            path: '/'
        }, {
            text: 'Page test',
            icon: Home,
            path: '/test'
        },
    ],
    open: () => {
        Drawer.state = true
    },
    close: () => {
        Drawer.state = false
    },
    toggle: () => {
        Drawer.state = !Drawer.state
    }
})
</script>

<template>
    <aside :opened="Drawer.state" ref="drawerRef">
        <AppDrawerItem v-for="item in Drawer.items" :key="item.text" :item="item" />
    </aside>

    <button @click.prevent="Drawer.toggle" v-if="!Drawer.state">
        <MaterialIconMenu />
    </button>
</template>

<style lang="scss" scoped>
aside {
    @apply bg-primary text-white font-semibold fixed w-56 h-full flex flex-col p-2 items-stretch gap-2 -translate-x-full transition-all duration-300;

    &[opened='true'] {
        @apply -translate-x-0;
    }
}

button {
    @apply p-3 bg-primary rounded-full fixed bottom-2 left-2 flex justify-center items-center text-white;
}
</style>
