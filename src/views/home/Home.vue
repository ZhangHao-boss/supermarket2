<template>
  <div id="home">
    <nav-bar class="nav-home"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banners="banners"></home-swiper>
  </div>
</template>

<script>
import NavBar from "../../components/common/navbar/NavBar";
import HomeSwiper from "./childComps/HomeSwiper";

import {getHomeMultidata} from "../../network/home";

export default {
  name: "Home",
  components:{
    NavBar,
    HomeSwiper
  },
  data(){
    return{
      banners:[],
      recommends:[]
    }
  },
  created() {
    getHomeMultidata().then((res)=>{
      console.log(res)
      this.banners=res.data.banner.list
      this.recommends=res.data.recommend
    })
  }
}
</script>

<style scoped>
.nav-home{
  background-color:var(--color-tint);
  color: aliceblue;
}
</style>
