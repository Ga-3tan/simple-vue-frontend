<script>
export default {
  data() {
    return {
      quote: "",
    }
  },
  methods: {
    async fetchQuote() {
      this.quote = await fetch('http://localhost:3000').then(
          res => res.text()
      ).catch(
          err => console.error(err)
      );
    }
  }
}
</script>

<template>
  <button @click="fetchQuote()">quote from backend</button>
  <p>{{ quote }}</p>
</template>
