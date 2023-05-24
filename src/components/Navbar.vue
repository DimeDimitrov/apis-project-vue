<template>
  <div class="flex items-center justify-center">
    <nav class="text-lg flex gap-6 text-white bg-slate-400 w-screen justify-center p-4">
      <router-link to="/">Home</router-link>
      <router-link to="/cat">Cat Facts</router-link>
      <router-link to="/joke">Jokes</router-link>
      <router-link to="/cat">Cat Facts</router-link>
      <router-link to="/cat">Cat Facts</router-link>
    </nav>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Navbar'
}
</script>
