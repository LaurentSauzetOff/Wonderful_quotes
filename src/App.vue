<template>
    <div class="container">
    <app-quote-grid :quotes="quotes"></app-quote-grid>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue'
    export default {
        components: {appQuoteGrid: QuoteGrid},
        data: function(){
            return {
                quotes: [
                    'Lire, c\'est refuser de mourir.'
                ],
                maxQuotes: 10
            }
        }
    }
</script>

<style>

@media screen and (min-width: 1200px){

    .container{
        margin: 0;
    }
}
</style>
