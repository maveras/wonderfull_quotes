<template>
<div class="row">
  <div class="alert alert-danger" v-if="quotes.length == 10">
    <strong>Info!</strong> You can't add more than 10 quotes
  </div>
  <div class="alert alert-info" v-if="quotes.length > 0">
    <strong>Info!</strong> Click on a quote to delete it!
  </div>
  <div class="col-md-12">
    <quote :quotes="quotes" @click.native="removeQuote(index)" v-for="(quote,index) in quotes" :keys="quote"> {{ quote }} </quote>
  </div>
</div>
</template>
<script>
  import quote from './quote.vue'
  export default {
    name:'quotes-grid',
    props:['quotes'],
    components:{
      quote
    },
    methods: {
      removeQuote (index) {
        this.$emit('removeQuote', index)
      }
    }
  }
</script>
<style>

</style>