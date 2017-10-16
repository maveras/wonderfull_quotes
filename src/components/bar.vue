<template>

  <div class="progress">
    <div class="progress-bar progress-bar-striped active" role="progressbar"
    aria-valuenow="40" aria-valuemin="0" aria-valuemax="100" :style="{width:width+'%'}">
    {{ numberQuotes }}
  </div>
</div>
</template>
<script>
export default {
  props:['quotes','maxQuotes'],
  computed: {
    numberQuotes () {
      return this.quotes.length
    },
    width () {
      return ((this.numberQuotes * 100)/this.maxQuotes)
    }
  }
}
</script>