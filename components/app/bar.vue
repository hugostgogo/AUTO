<script setup>
import MoonWaningCrescent from "vue-material-design-icons/MoonWaningCrescent.vue";
import CogOutline from "vue-material-design-icons/CogOutline.vue";
</script>



<template>
  <header>
    <div class="logo">
      <CogOutline />
    </div>
    <div class="title">
      <h1 class="rasp">Raspadio</h1>
    </div>
    <div class="rightSide">
      <MoonWaningCrescent />
    </div>
  </header>
</template>

<style lang="scss" scoped>
header {
  @apply px-4 py-4 shadow-md flex justify-between items-center;

  .logo {
    @apply text-primary scale-100 transition-all duration-500 drop-shadow-md;

    &:hover {
      @apply scale-125 ease-in-out rotate-180 cursor-pointer ;
    }
  }

.rasp {
    @apply font-bold text-2xl drop-shadow-md ;
}

}
</style>