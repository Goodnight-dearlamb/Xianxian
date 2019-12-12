<template>
  <div id="message">
    <el-row>
      <el-col :offset='1' :span="22">
        <p class="title">{{name}}</p>
        <p class="content">
          {{content}}
        </p>
        <el-divider content-position="right"><p class="time">{{time}}</p></el-divider>
      </el-col>
    </el-row>

  </div>
</template>

<script>
  export default {
    name: "message",
    data: function() {
      return {

      }
    },
    props:['name','time','content']
  }
</script>

<style>
  #message {
    width: 96%;
    margin: 9px auto;
    border-radius: 4px;
    background-color: white;
    box-shadow: 0 2px 4px rgba(0, 0, 0, .12), 0 0 6px rgba(0, 0, 0, .04)
  }

  .title {
    margin-top: 10px;
    font-size: 18px;
    line-height: 35px;
    color: black;
    opacity: .8;
  }
  .content{
    line-height:1.7;
    font-size: 14px;
    color: black;
    opacity: .7;
  }
  .time{
    color: black;
    opacity: .6;
    font-size: 12px;
  }
  .el-divider__text{

  }
</style>
