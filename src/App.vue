<script>
export default {
  data() {
    return {
      animal: "",
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
  <img src="https://picsum.photos/seed/picsum/1280/720" alt="S3 image"/>
</template>
