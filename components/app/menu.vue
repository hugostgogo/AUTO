<script setup>
import Home from 'vue-material-design-icons/Home.vue'
import { onClickOutside } from '@vueuse/core';
const menuRef = ref(null)

onClickOutside(menuRef, () => Menu.close())

const Menu = reactive({
    state: false,
    items: [
        {
            text: 'Home',
            icon: Home,
            path: '/'
        }, {
            text: 'Page test',
            icon: Home,
            path: '/test'
        },
    ],
    open: () => Menu.state = true,
    close: () => Menu.state = false,
    toggle: () => Menu.state = !Menu.state
})
</script>

<template>
    <div class="wrapper">
        <button @click="Menu.toggle">
            <MaterialIconMenu></MaterialIconMenu>
        </button>
        <Transition name="expand-y">
            <div class="menu" v-show="Menu.state" ref="menuRef">
                <AppMenuItem v-for="item in Menu.items" :key="item.text" :item="item" />
            </div>
        </Transition>
    </div>
</template>

<style lang="scss" scoped>
.wrapper {
    @apply relative;

    button {
        @apply text-primary w-10 h-10 flex items-center justify-center;
    }

    .menu {
        @apply absolute top-full right-0 bg-white shadow-md rounded-md w-48 py-2;
    }
}

.expand-y-enter-active,
.expand-y-leave-active {
  transition: all .3s ease-in-out;
}

.expand-y-enter-from,
.expand-y-leave-to {
    transform: translateY(-10%);
    opacity: 0;
}
</style>