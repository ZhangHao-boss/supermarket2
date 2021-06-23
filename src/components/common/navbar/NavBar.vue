<template>
  <div class="nav-bar">
    <div class="left"><slot name="left"></slot></div>
    <div class="center"><slot name="center"></slot></div>
    <div class="right"><slot name="right"></slot></div>
  </div>
</template>

<script>
export default {
  name: "NavBar"
}
</script>

<style scoped>
.nav-bar{
  display: flex;
  height: 40px;
  /*只有line-height属性，没有height属性，并且没有添加内容的话，盒子不会被撑开*/
  line-height: 44px;
  text-align: center;
  box-shadow: 0px 1px 1px rgba(100,100,100,.2);
}
.left,.right{
  width: 60px;
}
.center{
  flex: 1;
}
</style>