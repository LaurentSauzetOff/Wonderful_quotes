<template>
  <div class="container">
      <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @createdQuote="newQuoteAdded"></app-new-quote>
    <app-quote-grid
      :quotes="quotes"
      @quoteDeleted="deleteQuote"
    ></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Cliquez sur une citation pour la supprimer !
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuoteCompo from "./components/NewQuote.vue";
import Header from "./components/Header.vue";
export default {
  components: { appQuoteGrid: QuoteGrid, appNewQuote: NewQuoteCompo, appHeader: Header },
  data: function() {
    return {
      quotes: ["Lire, c'est refuser de mourir."],
      maxQuotes: 10
    };
  },
  methods: {
    newQuoteAdded(quote) {
        if (this.quotes.length >= this.maxQuotes){
            return alert('Veuillez supprimer des citations avant d\'en ajouter de nouvelles.')
        }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
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
