<script>
export default {
  data() {
    return {
      animal: "",
      image_url:import.meta.env.VITE_S3_IMAGE_URL,
    }
  },
  methods: {
    async fetchQuote() {
      this.animal = await fetch(import.meta.env.VITE_BACKEND_URL).then(
          res => res.text()
      ).catch(
          err => console.error(err)
      );
    }
  }
}
</script>

<template>
  <button @click="fetchQuote()">Get animal from backend</button>
  <p>{{ animal }}</p>
  <img :src="image_url" alt="S3 image"/>
</template>
