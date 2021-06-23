<template>
  <div id="home">
    <nav-bar class="nav-home"><div slot="center">购物街</div></nav-bar>
  </div>
</template>

<script>
import NavBar from "../../components/common/navbar/NavBar";
export default {
  name: "Home",
  components:{
    NavBar
  }
}
</script>

<style scoped>
.nav-home{
  background-color:var(--color-tint);
  color: aliceblue;
}
</style>
