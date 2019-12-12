<template>
  <div id="app">
    <Main />
  </div>
</template>

<script>
  import Main from './components/Main'

  export default {
    name: 'App',
    components: {
      Main
    }
  }
</script>

<style>
  * {
    padding: 0;
    margin: 0;
  }

  body,
  html {
    width: 100%;
  }

  p {
    font-family: "Helvetica Neue", Helvetica, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "微软雅黑", Arial, sans-serif;
  }

  #app{
    display: flex;
    background-color: rgb(245,245,245);
    width: 100%;
  }
  #Main{
    width: 100%;
    margin: 10px auto;
  }
</style>
