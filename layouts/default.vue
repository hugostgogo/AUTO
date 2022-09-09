<template>
    <div>
        <AppBar />
        <AppDrawer />
        <main>
            <slot />
        </main>
    </div>
</template>

<style lang="scss" scoped>
main {
    @apply
        p-2
    ;
}    
</style>