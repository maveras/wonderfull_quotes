<template>
  <div class="col-md-2 quote">
    <div class="img-quote">
      <img src="" alt="">
    </div>
    <div class="quote-content">
      <p><slot></slot></p>
    </div>
    <div class="quote-control">
      <ul class="quote-control__list">
        <li class="quote-control__list__item">
          back
        </li>
        <li class="quote-control__list__item">
          love
        </li>
        <li class="quote-control__list__item">
          share
        </li>
        <li class="quote-control__list__item">
          next
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name:'quote'
}
</script>
<style>
.quote {
  width:200px;
  height: 280px;
  border: solid 1px grey;
  display: inline-block;
  vertical-align: top;
  margin:20px;
}
</style>