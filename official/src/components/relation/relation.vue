<template>
  <div class="relation">
      <!-- 防止链接跳转 -->
     <a href="javascript:;" class="exit-off-canvas"></a>
      <div class="inside-banner"> <img src="../../assets/1569473641.jpg"/> </div>
      <el-card class="box-card">
    <el-tabs :before-leave="moreState">
      <el-tab-pane label="联系我们">联系我们</el-tab-pane>
      <el-tab-pane label="留言反馈">留言反馈</el-tab-pane>
      <el-tab-pane label="公告">公告</el-tab-pane>
      <el-tab-pane label="活动">活动</el-tab-pane>
      <el-tab-pane name="more" class="more-btn"><span slot="label"><router-link to="/page/wholeList/wholeList">更多+</router-link></span></el-tab-pane>
    </el-tabs>
  </el-card>
  </div>
</template>

<script>
export default {
  name: 'relation',
  data () {
    return {
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.relation{
    background-color: antiquewhite;
}
</style>
