<template>
  <main class="mt-7 max-w-sm mx-auto text-center card">
    <p class="mt-7 text-7xl font-bold">
      {{ error.statusCode }}
    </p>
    <p class="mt-7 text-6xl">Ooops.</p>
    <p class="mt-7">{{ error.message }}</p>
    <v-btn class="my-7" @click="handleClearError">Go Home...</v-btn>
  </main>
</template>

<script setup lang="ts">
  defineProps({
    error: {
      type: Object,
    },
  })

  const handleClearError = () => clearError({ redirect: '/' })
</script>

<style scoped></style>
