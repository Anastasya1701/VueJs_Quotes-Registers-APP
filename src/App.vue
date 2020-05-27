<template>
  <div class="container">
    <app-header :maxQuotes="maxQuotes" :quoteCount="quoteCount"></app-header>
    <app-quote-grid :quotes="quotes" @deleteQuote="deleteQuote"></app-quote-grid>
    <app-new-quote @newQuote="addNewQuote"></app-new-quote>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it</div>
      </div>
    </div>
  </div>
</template>

<script>
  import QuoteGrid from "./components/QuoteGrid";
  import NewQuote from "./components/NewQuote";
  import Header from "./components/Header";

  export default {
    data: function () {
      return {
        quotes: [
          'Just a quote to see something'
        ],
        maxQuotes: 10,
        quoteCount: 1,
      }
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote,
      appHeader: Header
    },
    methods: {
      addNewQuote(quote) {
        if (this.quotes.length >= this.maxQuotes) {
          return alert('Please delete Quotes first!');
        }
        this.quotes.push(quote)
        this.quoteCount += 1

      },
      deleteQuote(index) {
        this.quotes.splice(index, 1)
        this.quoteCount -= 1
      }
    }
  }
</script>

<style>
</style>
