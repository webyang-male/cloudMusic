<template>
  <div class="top-container">
    <div class="left-box">
      <a href="https://github.com/webyang-male/cloudMusic">✎项目源码</a>
    </div>
    <div class="site-name">
      💽 大赵的音乐屋 🎹
    </div>
    <div class="right-box">
      <div class="el-input el-input--small el-input--prefix">
        <!-- 搜索框 -->
        <input
          type="text"
          autocomplete="off"
          placeholder="搜索"
          class="el-input__inner"
          v-model="inputValue"
          @keyup.enter="toResult"
        />
        <span class="el-input__prefix">
          <i class="el-input__icon el-icon-search"></i>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "top",
  data() {
    return {
      inputValue: "",
    };
  },
  methods: {
    toResult() {
      if (this.inputValue == "") {
        this.$message({
          message: "搜索内容不能为空！",
          type: "warning",
        });
      } else {
        //this.$router.push(`/result?query=${this.inputValue}`)
        this.$router.push("/result?query=" + this.inputValue);
      }
    },
  },
};
</script>

<style scoped>
</style>
