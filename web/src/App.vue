<template>
<div>Bot昵称:{{bot_name}}</div>
  <router-view/>
</template>
<script>
  import $ from 'jquery';
  import {ref} from 'vue';
  export default{
    name:"APP",
    setup:()=>{
      let bot_name = ref("");
      $.ajax({
        url:"http://127.0.0.1:8888/pk/getbotinfo/",
        type:"get",
        success:resp =>{
         bot_name.value = resp;
        }
      });
      return{
        bot_name
      } 
    }
  }
</script>
<style>
</style>
