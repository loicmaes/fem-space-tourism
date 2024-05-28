<script setup lang="ts">
import { Menu, Xmark } from "@iconoir/vue";

const opened = ref<boolean>(false);

function setOpenState (state: boolean = false) {
  opened.value = state;
}
</script>

<template>
  <div class="wrapper">
    <button class="toggle" type="button" @click="setOpenState(true)"><Menu height="2rem" width="2rem" /></button>

    <nav class="nav" :class="{ opened }">
      <header class="nav__header">
        <button class="nav__header--close" @click="setOpenState(false)"><Xmark width="3rem" height="3rem" /></button>
      </header>

      <NuxtLink to="/" class="nav__link" active-class="active">
        <span class="nav__link--number">00</span>
        Home
      </NuxtLink>
      <NuxtLink to="/destination" class="nav__link" active-class="active">
        <span class="nav__link--number">01</span>
        Destination
      </NuxtLink>
      <NuxtLink to="/crew" class="nav__link" active-class="active">
        <span class="nav__link--number">02</span>
        Crew
      </NuxtLink>
      <NuxtLink to="/technology" class="nav__link" active-class="active">
        <span class="nav__link--number">03</span>
        Technology
      </NuxtLink>
    </nav>
  </div>
</template>

<style scoped lang="sass">
.wrapper
  @apply relative

.toggle
  @apply aspect-square w-12 grid place-items-center md:hidden

.nav
  @apply translate-x-[100%] transition-transform md:translate-x-0 z-20 md:z-0 max-w-72 w-full md:w-auto md:max-w-none fixed right-0 inset-y-0 md:relative md:right-auto md:inset-y-auto flex flex-col md:flex-row md:items-center gap-8 md:gap-12 pl-8 md:pl-28 lg:pl-40 md:pr-10 lg:pr-16 bg-darkish/15 md:bg-white/5 backdrop-blur-xl

  &.opened
    @apply translate-x-0

  &__header
    @apply md:hidden py-8 pr-6 flex shrink-0 items-center justify-end

    &--close
      @apply text-blue

  &__link
    @apply min-w-52 md:min-w-0 relative md:py-10 tracking-[2px] uppercase flex items-center gap-3 before:absolute before:w-[3px] md:before:w-auto md:before:h-[3px] before:opacity-50 before:inset-y-0 before:right-0 md:before:top-auto md:before:bottom-0 md:before:inset-x-0 before:bg-white before:scale-y-0 md:before:scale-y-100 md:before:scale-x-0 before:transition-transform hover:before:scale-100

    &.active
      @apply before:opacity-100 before:scale-100

    &--number
      @apply tracking-[3px] font-bold
</style>
