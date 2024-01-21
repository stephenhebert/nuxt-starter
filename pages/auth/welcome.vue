<script setup lang="ts">
import { useUser } from 'vue-clerk'
import { ref } from 'vue'
import { until } from '@vueuse/core'

definePageMeta({
  middleware: ['auth'],
  layout: 'centered',
})

const { user } = useUser()

await until(user).toBeTruthy()
const name = ref(user.value?.fullName)

async function createUser(form) {
  const response = await fetch('/api/profile', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify(form)
  })
  if (response.ok) {
    // TODO: go back to returnUrl
    navigateTo('/')
  }
}

</script>

<template>
  <div>
    <div>Welcome!</div>

    <FormKit
      type="form"
      name="profile"
      submit-label="Continue"
      @submit="createUser"
    >
      <FormKit
        type="text"
        name="name"
        label="Your name"
        v-model="name"
        validation="required"
      />
    </FormKit>
  </div>
</template>