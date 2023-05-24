<template>
  <div class="flex flex-col items-center justify-center h-20 gap-10">
    <Navbar />
  </div>
  <div class="flex flex-col items-center justify-center h-20 gap-10">
    <router-view />
  </div>
</template>

<script lang="ts">
import Navbar from './components/Navbar.vue'

export default {
  name: 'App',
  components: {
    Navbar
  }
}
</script>
