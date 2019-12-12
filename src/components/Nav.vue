<template>
  <div id="XNav">
    <el-button icon="el-icon-ice-tea" class="setting" circle></el-button>
    <el-row>
      <el-col :offset="1" :span="22">
        <i class="el-icon-watermelon" style="font-size: 1.5rem;" @click="change"></i>
      </el-col>
    </el-row>
    <Left ref="left" />
  </div>
</template>

<script>
import Left from "../components/Left";

export default {
  name: "XNav",
  data: function() {
    return {
      address: "",
      temperature: "",
      weather: ""
    };
  },
  methods: {
    change: function() {
      this.$refs["left"].change();
    }
  },
  computed: {},
  components: { Left }
};
</script>

<style>
#XNav {
  width: 100%;
}

.el-drawer {
  width: 70% !important;
}

.setting {
  color: pink;
  font-size: 1.2rem;
  position: fixed;
  z-index: 111111;
  right: 10px;
  bottom: 10px;
}

.data {
  display: inline;
}
</style>
