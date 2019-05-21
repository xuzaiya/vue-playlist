<!--1.模板html结构-->
<template>
  <div id="app">
    <ul>
      <!--<li><a href="/">Home</a></li>-->
      <!--<li><a href="/helloworld">HelloWorld</a></li>-->
      <li><router-link to="/">HOME</router-link></li>
      <li><router-link to="/helloworld">HelloWorld</router-link></li>
    </ul>
    <router-view></router-view>
  </div>
</template>
<!--2.行为：处理逻辑-->
<script>
  //局部注册组件

export default {
  name: 'App',
  data(){
    return{

      title:"传递的是一个值,(number string boolean)"
    }
  },






}
</script>
<!--3.样式：解决样式-->
<style scoped>
  h1{
    color:yellow;
  }
</style>
