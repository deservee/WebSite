<template>
  <div class="foot">
      <h1>{{ msg }}</h1>
      
  </div>
</template>

<script>
export default {
  name: 'foot',
  data () {
    return {
      msg: '222 '
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.foot{
    background-color: antiquewhite;
}
</style>