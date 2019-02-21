<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
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
    import Header from './components/Header.vue';

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
                if (quote) {
                    if (this.quotes.length >= this.maxQuotes) {
                        return alert("You exceeded the maximum limit of quotes!\nPlease delete quotes to add new.")
                    } else {
                        this.quotes.push(quote);
                    }
                }
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        }
    }
</script>

<style>

</style>
