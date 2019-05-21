<template>
  <div class="user">
    <h1>Hello user</h1>
    <ul>
      <li v-for="user in users" >
          <h2>{{user.name}}</h2>
          <h3>{{user.email}}</h3>
      </li>
    </ul>
    <button v-on:click="deleteUser">删除</button>
  </div>

</template>
<!--
  父子组件传值
  传值：string number boolean
  传引用：array object
  (传引用，如果一个地方的值发生变化，整个用到该应用的地方
  都会发生变化)
  传值的话，改变一个，只改变这一个，别的不变
-->
<script>
    export default {
        name: "User",
        //props:["users"],
      props:{
        users:{
          type:Array,
          require:true
        },

      },
      data(){
          return{

          }
      },
      methods:{
        deleteUser:function () {
          this.users.pop();
        }
      }
    }
</script>


<style scoped>
  h1{
    color:green;
  }
  .user{
    width: 100%;
    max-width: 1200px;
    margin:40px auto;
    padding:0 20px;
    box-sizing: border-box;
  /*<!-- 给个这个就不用计算padding -->*/
  }

  ul{
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
  }
  li{
    /*//如果有一个撑满整行，有两个，两个撑满整行*/
    flex-grow: 1;
    flex-basis: 200px;
    text-align: center;
    padding: 30px;
    border: 1px solid #222;
    margin:10px;
  }
</style>
