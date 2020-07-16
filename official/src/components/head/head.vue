<template>
  <div class="head">
      <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'head',
  data () {
    return {
      msg: '1111 '
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.head{
    background-color: antiquewhite;
}
</style>
