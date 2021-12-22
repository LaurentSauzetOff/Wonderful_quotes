<template>
  <div class="container">
      <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes"></app-quote-grid>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
export default {
  components: { appQuoteGrid: QuoteGrid,  appNewQuote: NewQuote},
  data: function() {
    return {
      quotes: ["Lire, c'est refuser de mourir."],
      maxQuotes: 10
    };
  },
  methods: {
      newQuote(quote){
          this.quotes.push(quote);
      }
  }
};
</script>

<style>
@media screen and (min-width: 1200px) {
  .container {
    margin: 0;
  }
}
</style>
