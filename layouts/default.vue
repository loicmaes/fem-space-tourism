<script setup lang="ts">

import Logo from "~/components/layout/brand/Logo.vue";
</script>

<template>
  <div class="layout">
    <header class="header">
      <Logo />

      <hr class="header--separator" />

      <nav class="header__nav">
        <NuxtLink to="/" class="header__nav__link" active-class="active">
          <span class="header__nav__link--number">00</span>
          Home
        </NuxtLink>
        <NuxtLink to="/destination" class="header__nav__link" active-class="active">
          <span class="header__nav__link--number">01</span>
          Destination
        </NuxtLink>
        <NuxtLink to="/crew" class="header__nav__link" active-class="active">
          <span class="header__nav__link--number">02</span>
          Crew
        </NuxtLink>
        <NuxtLink to="/technology" class="header__nav__link" active-class="active">
          <span class="header__nav__link--number">03</span>
          Technology
        </NuxtLink>
      </nav>
    </header>

    <slot />
  </div>
</template>

<style lang="sass" scoped>
.layout
  @apply relative

.header
  @apply fixed z-10 top-10 inset-x-0 pl-16 flex items-center gap-4 isolate

  &--separator
    @apply border-[1px] border-white opacity-25 grow z-10 translate-x-8

  &__nav
    @apply flex items-center gap-12 pl-40 pr-16 bg-white/5 backdrop-blur-xl

    &__link
      @apply relative py-10 tracking-[2px] uppercase flex items-center gap-3 before:absolute before:h-[3px] before:bottom-0 before:inset-x-0 before:bg-white before:opacity-0 before:translate-y-3 before:transition-all hover:before:opacity-50 hover:before:translate-y-0

      &.active
        @apply before:opacity-100 before:translate-y-0

      &--number
        @apply tracking-[3px] font-bold
</style>
