<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuote="maxQuotes"></app-header>
    <app-new-quotes @quoteAdded="newQuote"></app-new-quotes>
    <app-quotes-grid :quotes="quotes" @quoteDeleted="deleteQuoted"></app-quotes-grid>
    <div class="col-sm-12 mt-5">
      <div class="alert alert-info text-center">info: click on a quote to delete</div>
    </div>
  </div>
</template>

<script>
import QuotesGrid from "./components/QuotesGrid.vue";
import NewQuotes from "./components/NewQuotes.vue";
import Header from "./components/Header.vue";
export default {
  data() {
    return {
      quotes: ["just simple quotes"],
      maxQuotes: 10
    };
  },
  methods: {
    newQuote(quote) {
        if (this.quotes.length >= this.maxQuotes) {
            return alert("delete a quote")
        }
      this.quotes.push(quote);
    },
    deleteQuoted(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appQuotesGrid: QuotesGrid,
    appNewQuotes: NewQuotes,
    appHeader: Header
  }
};
</script>

