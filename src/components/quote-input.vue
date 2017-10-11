<template>
  <div class="form-group">
    <label for="comment">quote:</label>
    <textarea class="form-control" rows="5" v-model="quoteContent"></textarea>
    <button class="btn btn-success">Add quote</button>
  </div>
</template>
<script>
  export default {
    data (){
      return {
        quoteContent: ''
      }
    },

  }
</script>
<style>
  
</style>