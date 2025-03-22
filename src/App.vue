<script setup>
import { RouterView } from 'vue-router'
import Header from '@/components/Layout/Header.vue'
</script>

<template>
  <Header />

  <main class="bg-gray-900">
    <RouterView />
  </main>
</template>
