<template>
<!--  <div>分类</div>-->
  <div class="wrapper">
    <ul class="content">
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
      <li>靓仔</li>
    </ul>
  </div>
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: "Category",
  data(){
    return{
      scroll:null
    }
  },
  mounted() {
    this.scroll=new BScroll(document.querySelector('.wrapper'),{
      probeType:3,
      pullUpLoad:true,
      // click:true
    })
    //监听滚动位置
    this.scroll.on('scroll',(position)=>{
      //betterscroll元素打印滑到的位置
      console.log(position)
    })
    //上拉加载内容
    this.scroll.on('pullingUp',()=>{
      console.log('上拉加载更多')
    })
  }
}
</script>

<style scoped>
 .wrapper{
   height: 120px;
   background-color: red;
   overflow: hidden;
   /*overflow-y: scroll;*/
   /*overflow: auto;*/
 }
</style>
