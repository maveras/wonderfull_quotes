<template>
  <div class="container">
    <bar :quotes="quotes" :maxQuotes="maxQuotes"></bar>
    <quote-input></quote-input>
    <app-quotes-grid :quotes="quotes" @removeQuote='removeQuote'></app-quotes-grid>
  </div>
</template>

<script>
import appQuotesGrid from './components/quotes-grid.vue'
import quoteInput from './components/quote-input.vue'
import bar from './components/bar.vue'

import {eventBus} from './main'
export default {
  name: 'app',
  data () {
    return {
      quotes: ['first quote','second quote'],
      maxQuotes: 10
    }
  },
  methods: {
    removeQuote(index){
      this.quotes.splice(index, 1)
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
    quoteInput,
    bar
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
