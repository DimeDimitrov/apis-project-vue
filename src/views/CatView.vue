<template>
  <div class="flex justify-center items-center flex-col gap-10">
    <button
      @click="getRandomCatFact(), getRandomCatImage()"
      class="text-white text-3xl bg-slate-500 border-slate-800-2 p-4 w-fit mt-10"
    >
      Get Random Cat Fact
    </button>
  </div>
  <div class="flex flex-col p-10 justify-center items-center">
    <p v-if="randomFact" class="text-white text-3xl">{{ randomFact }}</p>

    <img
      v-if="randomCatImage"
      :src="randomCatImage"
      alt="Random Cat"
      style="max-width: 400px; margin-top: 10px"
    />
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      randomFact: '',
      randomCatImage: ''
    }
  },
  methods: {
    getRandomCatFact() {
      fetch('https://catfact.ninja/fact')
        .then((response) => response.json())
        .then((data) => {
          this.randomFact = data.fact
        })
        .catch((error) => {
          console.error(error)
        })
    },
    getRandomCatImage() {
      fetch('https://api.thecatapi.com/v1/images/search')
        .then((response) => response.json())
        .then((data) => {
          this.randomCatImage = data[0].url
        })
        .catch((error) => {
          console.error(error)
        })
    }
  }
}
</script>

<style lang=""></style>
