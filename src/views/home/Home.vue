<template>
  <div id="home">
    <nav-bar class="nav-home"><div slot="center">购物街</div></nav-bar>
    <scroll class="content"
            ref="scroll"
            :probe-type="3"
            :pull-up-load="true"
            @scroll="contentScroll"
            @pullingUp="loadMore">
      <home-swiper :banners="banners"></home-swiper>
      <recommend-view :recommends="recommends"></recommend-view>
      <feature-view></feature-view>
      <tab-control :titles="['流行','新款','精选']" class="tab-control" @tabClick="tabClick"></tab-control>
      <goods-list :goods="goods[currentType].list"></goods-list>
    </scroll>
    <back-top @click.native="backClick" v-show="isShowBackTop"></back-top>
  </div>
</template>

<script>
import HomeSwiper from "./childComps/HomeSwiper";
import RecommendView from "./childComps/RecommendView";
import featureView from "./childComps/featureView";

import NavBar from "../../components/common/navbar/NavBar";
import TabControl from "../../components/content/tabControl/TabControl";

import GoodsList from "../../components/content/goods/GoodsList";
import BackTop from "../../components/content/backTop/BackTop";
import Scroll from "../../components/common/scroll/Scroll";

import {getHomeMultidata,getHomeGoods} from "../../network/home";

export default {
  name: "Home",
  components:{
    HomeSwiper,
    RecommendView,
    featureView,
    NavBar,
    TabControl,
    GoodsList,
    Scroll,
    BackTop
  },
  data(){
    return{
      banners:[],
      recommends:[],
      //设置商品的数据结构
      goods:{
        'pop':{page:0,list:[]},
        'new':{page: 0,list: []},
        'sell':{page: 0,list: []}
      },
      currentType:'pop',
      isShowBackTop:false
    }
  },
  created() {
    this.getHomeMultidata()
    this.getHomeGoods('pop')
    this.getHomeGoods('new')
    this.getHomeGoods('sell')
  },
  methods:{
    /**
     * 事件监听相关的方法
     * **/
    tabClick(index){
      // console.log(index)
      switch (index){
        case 0:
          this.currentType='pop'
          break
        case 1:
          this.currentType='new'
          break
        case 2:
          this.currentType='sell'
          break
        default:break
      }
    },

    /**
      网络请求相关的方法
    * */
    getHomeMultidata(){
      getHomeMultidata().then((res)=>{
        // console.log(res)
        this.banners=res.data.banner.list
        this.recommends=res.data.recommend.list
      })
    },
    //得到HomeGoods数据
    getHomeGoods(type){
      const page=this.goods[type].page+1
      getHomeGoods(type,page).then((res)=>{
        // console.log(res);
        this.goods[type].list.push(...res.data.list)
        this.goods[type].page+=1

        this.$refs.scroll.scroll.finishPullUp()
      })
    },
    //返回首页
    backClick(){
      //this.$refs.scroll获取ref=scroll的元素
      //this.$refs.scroll.scroll获取scroll中scroll数据
      this.$refs.scroll.scroll.scrollTo(0,0,500)
    },
    //显示与隐藏BackTop组件
    contentScroll(position){
      // if (position.y<-1000){
      //   this.isShowBackTop=true
      // }else {
      //   this.isShowBackTop=false
      // }
      //也可以直接写成下面的一句
      this.isShowBackTop=position.y<(-1000)
    },
    //上拉加载更多内容
    loadMore(){
      this.getHomeGoods(this.currentType)
      //解决下拉图片卡顿的bug
      this.$refs.scroll.scroll.refresh()
    }
  }
}
</script>

<style scoped>
.nav-home{
  background-color:var(--color-tint);
  color: aliceblue;
  position: sticky;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
}
#home{
  /*padding-bottom: 49px;*/
  height:100vh;
}
.tab-control{
  position: sticky;
  top: 40px;
  z-index: 9;
}
.content{
  height:calc(100% - 85px);
  overflow: hidden;
}
</style>
