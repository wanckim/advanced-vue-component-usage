<template>
    <div class="container">
        <app-new-quote @quoteAdded="newQuote($event)"></app-new-quote>
        <app-quote-grid :quotes='quotes' @quoteSelected="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">info: Click on a quote to delete it!</div>
            </div>
        </div>
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
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
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
