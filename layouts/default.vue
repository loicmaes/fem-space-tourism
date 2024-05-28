<script setup lang="ts">

import Logo from "~/components/layout/brand/logo.vue";
import Navigation from "~/components/layout/navigation.vue";
</script>

<template>
  <div class="layout">
    <header class="header">
      <Logo />

      <hr class="header--separator" />

      <Navigation />
    </header>

    <slot />
  </div>
</template>

<style lang="sass" scoped>
.layout
  @apply relative

.header
  @apply fixed z-10 top-6 lg:top-10 inset-x-0 px-6 md:pl-10 lg:pl-16 md:pr-0 flex items-center justify-between gap-4 isolate

  &--separator
    @apply hidden lg:block border-[1px] border-white opacity-25 grow z-10 translate-x-8
</style>
