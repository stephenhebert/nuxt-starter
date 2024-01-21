<script setup lang="ts">
import theme from '@/theme'
import { ModalContainer } from '@stephenhebert/vue-use-modal'

const route = useRoute()
const computedTitle = computed(() => {
  const title = route.meta?.title
  return title ? `${title} | My App` : 'My App'
})

useHead({
  title: computedTitle,
})
</script>

<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
    <ThemeProvider :theme="theme" />
    <ModalContainer />
  </div>
</template>
