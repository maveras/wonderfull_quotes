<template>
<div class="row">
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