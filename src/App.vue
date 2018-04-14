<template>
    <div class="container">
        <h1>Quotes Added</h1>

        <app-progress :max="maxQuotes" :actual="quotesCounter"></app-progress>

        <app-quote-form @quoteAdded="newQuote"></app-quote-form>

        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>

        <div class="alert alert-info" role="alert">
            <strong>Info:</strong> Click on a Quote to delete it.
        </div>

    </div>
</template>

<script>
    import Progress from './components/Progress.vue';
    import QuoteGrid from './components/QuoteGrid.vue';
    import QuoteForm from './components/QuoteForm.vue';

    export default {
        data(){
            return {
                quotes: [
                    'Just a Quote to start with something'
                ],
                maxQuotes: 10
            };
        },

        components: {
            appProgress: Progress,
            appQuoteGrid: QuoteGrid,
            appQuoteForm: QuoteForm
        },

        computed: {
            quotesCounter(){
                console.log(this.quotes.length);
                return this.quotes.length;
            }
        },

        methods: {
            newQuote(quote){
                if (this.quotesCounter == this.maxQuotes){
                    alert('Please delete Quotes first!');
                    return;
                }

                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>
</style>
