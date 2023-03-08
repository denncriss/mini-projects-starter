<template>
  <main>
    <QuoteBox :quote="quote" :color="color" @changeQuote="changeQuote" />
  </main>
</template>

<script setup>
  import QuoteBox from './components/quoteBox.vue';
  import { ref } from 'vue';
  const quote = ref({
    quote: 'La felicidad lo encuentras programando en VUE JS',
    from: 'denncriss',
  });
  const color = ref('#20dab7');

  const changeQuote = () => {
    console.log('tenemos que buscar una nueva quote');
  };
</script>
