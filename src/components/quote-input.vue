<template>
  <div class="form-group">
    <label for="comment">quote:</label>
    <textarea class="form-control" rows="5" v-model="quoteContent"></textarea>
    <button class="btn btn-success" @click="addQuote">Add quote</button>
  </div>
</template>
<script>
  import {eventBus} from '../main'
  export default {
    data (){
      return {
        quoteContent: ''
      }
    },
    methods: {
      addQuote () {
        eventBus.pushQuote(this.quoteContent)
        this.quoteContent = ''
      }
    }

  }
</script>
<style>
  
</style>