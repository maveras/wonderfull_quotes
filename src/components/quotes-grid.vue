<template>
<div class="row">
  <div class="col-md-12">
    <quote v-for="quote in quotes" :keys="quote"> {{ quote }}</quote>
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
    }
  }
</script>
<style>

</style>