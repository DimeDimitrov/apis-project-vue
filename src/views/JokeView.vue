<template>
  <div>
    <button @click="getRandomFact">Get Random Joke</button>
    <p v-if="setup">{{ setup }}</p>
    <button @click="togglePunchlineDisplay">Click me!</button>
    <p v-if="punchlineDisplay">{{ punchline }}</p>
  </div>
</template>

<script lang="ts">
import { ref } from 'vue'

export default {
  setup() {
    const setup = ref('')
    const punchline = ref('')
    const punchlineDisplay = ref(false)

    const togglePunchlineDisplay = () => {
      punchlineDisplay.value = !punchlineDisplay.value
    }

    const getRandomFact = () => {
      fetch('https://official-joke-api.appspot.com/random_joke')
        .then((response) => response.json())
        .then((data) => {
          setup.value = data.setup
          punchline.value = data.punchline
          punchlineDisplay.value = false // Reset punchline display when fetching a new joke
        })
        .catch((error) => {
          console.error(error)
        })
    }

    return {
      setup,
      punchline,
      punchlineDisplay,
      togglePunchlineDisplay,
      getRandomFact
    }
  }
}
</script>

<style lang=""></style>
