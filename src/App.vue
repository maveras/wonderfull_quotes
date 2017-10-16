<template>
  <div class="container">
    <quote-input></quote-input>
    <app-quotes-grid :quotes="quotes"></app-quotes-grid>
  </div>
</template>

<script>
import appQuotesGrid from './components/quotes-grid.vue'
import quoteInput from './components/quote-input.vue'

import {eventBus} from './main'
export default {
  name: 'app',
  data () {
    return {
      quotes: ['first quote','second quote'],
      maxQuotes: 10
    }
  },
  computed: {
    quotesQty() {
      return this.quotes.length
    }
  },
  created () {
    eventBus.$on('pushQuote',(quote)=>{
      if(this.quotesQty < 10) {
        this.quotes.push(quote)
      }
    })
  },
  components: {
    appQuotesGrid,
    quoteInput
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
