<template>
  <div>
    <button @click="getRandomFact">Get Random Fact</button>
    <p v-if="randomFact">{{ randomFact }}</p>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      randomFact: ''
    }
  },
  methods: {
    getRandomFact() {
      fetch('https://catfact.ninja/fact')
        .then((response) => response.json())
        .then((data) => {
          this.randomFact = data.fact
        })
        .catch((error) => {
          console.error(error)
        })
    }
  }
}
</script>

<style lang=""></style>
