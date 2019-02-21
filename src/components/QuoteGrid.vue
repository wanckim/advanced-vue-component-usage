<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" @click.native="selectQuote(index)">
            {{ quote }}
        </app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';

    export default {
        props: ['quotes'],
        components: {
            appQuote: Quote
        },
        methods: {
            selectQuote(index) {
                this.$emit('quoteSelected', index);
            }
        }
    }
</script>

<style scoped>
</style>
