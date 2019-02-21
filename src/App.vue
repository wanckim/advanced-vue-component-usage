<template>
    <div class="container">
        <app-new-quote @quoteAdded="newQuote($event)"></app-new-quote>
        <app-quote-grid :quotes='quotes'></app-quote-grid>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';

    export default {
        data: function() {
            return {
                quotes: [
                    'Sample quote'
                ],
                maxQuotes: 10
            }
        },
        methods: {
            newQuote(quote) {
                quote ? this.quotes.push(quote) : null;
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote
        }
    }
</script>

<style>

</style>
