<template>
  <section class="advice-section">
    <AdviceBox :quote="quote" :getAdvice="getAdvice" />
  </section>
</template>

<script>
import AdviceBox from './components/AdviceBox.vue';

export default {
  data() {
    return {
      API: 'https://api.adviceslip.com/advice',
      quote: {
        id: 0,
        content: "..."
      }
    }
  },
  components: {
    AdviceBox
  },
  created() {
    this.getAdvice();
  },
  methods: {
    async getAdvice() {
      let request = await fetch(this.API);
      let data = await request.json();

      this.quote.id = data.slip.id;
      this.quote.content = data.slip.advice;
    }
  }
}
</script>

<style scoped>
/* Section Styles */
.advice-section {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
</style>
