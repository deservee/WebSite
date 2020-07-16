<template>
  <div id="app">
    <Relation />
    <router-view/>
  </div>
</template>

<script>
// import Head from './components/head/head'
// import Login from './components/login/login'
// import Foot from './components/foot/foot'
import Relation from './components/relation/relation'
export default {
  name: 'App',
  components:{
    //Head, 
    //Login,
    Relation
  }
}
</script>

<style>
    /* @import'../static/css/index.css' */

</style>
