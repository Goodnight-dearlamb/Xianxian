<template>
  <div id="Main">
    <XNav />
  <Message v-for="item in list" :key="item.id" :name="item.name" :content="item.content" :time="item.time"></Message>
  </div>
</template>

<script>
  import Message from "../components/Content"
  import XNav from "../components/Nav"
  export default {
    name:"Main",
    data:function(){
      return {
        list:''
      }
    },
    components:{Message,XNav},
    created:function(){
      this.axios.get("http://6s.net579.com:10675/xianxian/public/index/index/listCont")
      .then(res => {
        this.list = res.data
      })
      .catch(e => {
        console.log(e);
      })
    }
  }
</script>

<style>

</style>
