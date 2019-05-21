<!--1.模板html结构-->
<template>
  <div id="home">
    <!--子组件向父组件传值
      要注册一个事件，并且名字要和父组件绑定的方法名字要一样
      子组件传递过来一个参数，在父组件里面要接受一个参数，$event，必须是这个
    -->
    <app-header v-on:titleChanged="updateTitle($event)" v-bind:title="title"></app-header>
    <user v-bind:users="users"></user>
    <user v-bind:users="users"></user>
    <app-footer v-bind:title="title"></app-footer>

  </div>
</template>
<!--2.行为：处理逻辑-->
<script>
  //局部注册组件
  import User from './User'
  import Header from './Header'
  import Footer from './Footer'
  export default {
    name: 'home',
    data(){
      return{
        users:[
        //   {name:'Henry',position:'WEB开发',show:false},
        //   {name:'yangxu',position:'后端开发',show:false},
        //   {name:'yangjie',position:'前端开发',show:false},
        //   {name:'liugang',position:'全站开发',show:false},
        //   {name:'zhanghai',position:'网站开发',show:false},
        //   {name:'zhanghai',position:'网站开发',show:false},
        //   {name:'zhanghai',position:'网站开发',show:false},
        //   {name:'zhanghai',position:'网站开发',show:false},
        //   {name:'zhanghai',position:'网站开发',show:false},
        //   {name:'zhanghai',position:'网站开发',show:false},
        //
        ],
        title:"传递的是一个值,(number string boolean)"
      }
    },
    methods:{
      updateTitle(e){
        this.title = e;
      }
    },




    //局部注册组件
    components:{
      'user':User,
      'app-header':Header,
      'app-footer':Footer,
    },
    created(){
      this.$http.get("http://jsonplaceholder.typicode.com/users")
        .then((data) => {
          //console.log(data);
          this.users = data.body;
        })
    },

  }
</script>
<!--3.样式：解决样式-->
<style>
  h1{
    color:yellow;
  }
</style>
