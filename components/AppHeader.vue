<script setup>

</script>

<template>
  <div class="sticky top-0 z-100 min-w-320px w-full border-b-1 border-gray-700 bg-white shadow-lg">
    <div class="m-auto max-w-900px flex items-center justify-between sm:p-4 lt-sm:(px-4 py-2)">
      <div class="fw-900 font-title lt-sm:text-lg sm:text-2xl">
        <NuxtLink to="/">
          My App
        </NuxtLink>
      </div>
      <ul class="flex flex-row font-title divide-x lt-sm:text-xs">
        <li class="px-2">
          <NuxtLink to="/">
            <span class="text-gray-600 hover:text-black">Link</span>
          </NuxtLink>
        </li>
      </ul>
      <div>
        <!-- <AppUser /> -->
      </div>
    </div>
  </div>
</template>