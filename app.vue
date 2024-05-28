<template>
  <IconoirProvider :icon-props="{
    'width': '1.5rem',
    'height': '1.5rem',
    'stroke-width': '1.5',
  }">
    <NuxtLoadingIndicator />

    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </IconoirProvider>
</template>

<script setup lang="ts">
import { IconoirProvider } from "@iconoir/vue";
</script>
