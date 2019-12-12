<template>
  <div id="Left">
    <el-drawer :visible.sync="drawer" :append-to-body="true" direction="ltr">
      <div class="topImg">
        <div class="wendu">
          <p>{{wendu}}°  {{tianqi}}</p>
          <p>{{address}}</p>
        </div>
      </div>
      <div class="settingl">
        <p>会填坑的</p>
        <p>先用着吧</p>
        <p>年前可能一直加班</p>
      </div>
    </el-drawer>
  </div>
</template>

<script>
  export default {
    name: "Left",
    data: function() {
      return {
        drawer: false,
        wendu: '显示不出来告诉我一哈',
        tianqi:'',
        address:''
      }
    },
    methods: {
      change: function() {
        this.drawer = true
      }
    },
    created: function() {
      this.axios.get("https://v2.jinrishici.com/info")
        .then(res => {
          this.wendu = res.data.data.weatherData.temperature;
          this.tianqi  = res.data.data.weatherData.weather;
          this.address = res.data.data.region
        })
        .catch(e => {
          console.log(e);
        })
    }
  }
</script>

<style>
  .contentl {
    display: flex;
    flex-flow: column;
  }

  .topImg {
    height: 30%;
    overflow: hidden;
    background-image: url(../../static/img/ba.jpg);
    background-size: 100% auto;
    display: flex;
  }

  .wendu{
    margin: auto;
  }

  .wendu>p{
     font-size: 20px;
     opacity: .4;
  }

  .settingl {
    height: 70%;
    text-align: center;
    color: gray;
  }
  .settingl>p{
    line-height: 1.7rem;
  }

  .el-drawer__header {
    display: none;
  }
</style>
