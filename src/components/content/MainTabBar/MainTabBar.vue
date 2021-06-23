<template>
<div>
  <TabBar>
    <tab-bar-item path="/home" activeColor="cornflowerblue">
      <img src="@/assets/img/tabbar/shouye.svg" alt="" slot="item-icon">
      <img src="@/assets/img/tabbar/shoyexuan.svg" alt="" slot="item-icon-active">
      <div slot="item-text">首页</div>
    </tab-bar-item>
    <tab-bar-item path="/category" activeColor="cornflowerblue">
      <img src="@/assets/img/tabbar/fenlei.svg" alt="" slot="item-icon">
      <img src="@/assets/img/tabbar/fneleixuan.svg" alt="" slot="item-icon-active">
      <div slot="item-text">分类</div>
    </tab-bar-item>
    <tab-bar-item path="/cart" activeColor="cornflowerblue">
      <img src="@/assets/img/tabbar/gouwuche.svg" alt="" slot="item-icon">
      <img src="@/assets/img/tabbar/gouwuchexuan.svg" alt="" slot="item-icon-active">
      <div slot="item-text">购物车</div>
    </tab-bar-item>
    <tab-bar-item path="/profile" activeColor="cornflowerblue">
      <img src="@/assets/img/tabbar/wode.svg" alt="" slot="item-icon">
      <img src="@/assets/img/tabbar/wodexuan.svg" alt="" slot="item-icon-active">
      <div slot="item-text">我的</div>
    </tab-bar-item>
  </TabBar>
</div>
</template>

<script>
import TabBar from "../../common/tabbar/TabBar";
import TabBarItem from "../../common/tabbar/TabBarItem";

export default {
  name: "MainTabBar",
  components:{
    TabBar,
    TabBarItem
  }
}
</script>

<style scoped>

</style>
