<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import AppHeader from './components/organisms/AppHeader.vue';
import AppFooter from './components/organisms/AppFooter.vue';
</script>

<template>
  <AppHeader></AppHeader>

  <main>
    <RouterView />
  </main>

  <AppFooter></AppFooter>
</template>

<style lang="css" scoped>

</style>
