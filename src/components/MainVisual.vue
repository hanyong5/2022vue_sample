<template>
  <div class="visual">
    <Swiper
    v-bind="swiperOptions"
    :modules="modules"
    class="mySwiper"
    >
      <swiper-slide class="item" v-for="item in swiperView" :key="item">
        <div :style="{'background-color':`${item.color}`}" class="imgWrap">
          <img :src="`images/billboards/${item.src}`" alt="">

        </div>
        <!-- {{item.name}} -->
      </swiper-slide>
      <button class="prev">이전</button>
      <button class="next">다음</button>
    </Swiper>
  </div>
</template>

<script>
import {Swiper,SwiperSlide} from "swiper/vue";
import "swiper/css"

import "swiper/css/pagination";
import "swiper/css/navigation";

// import required modules
import { Pagination, Navigation } from "swiper";
import sData from "../data/swiper.js"


export default {
  components:{
    Swiper,
    SwiperSlide,
  },
  data(){
    return {
      swiperView:sData,
      modules:[Pagination,Navigation],
      swiperOptions:{
        loop:true,
        navigation: {
            nextEl: '.visual .next',
            prevEl: '.visual .prev'
          }
      }
    }
  },

}
</script>

<style lang="scss">
    .visual{
        min-width:1280px;
        margin-bottom: 20px;
        .item{
          // height: 300px;
          display: flex;
          justify-content: center;
          align-items: center;
        }
        img{ display: block;margin: 0 auto}
        .imgWrap{ 
          width: 100%;
        }
        .swiper-pagination{ 
          display:inline-block;
          background:rgba(0,0,0,0.2);
          width: 100px;
          padding: 15px;
          position: absolute;
          left: calc( 50% + 450px );
          border-radius:30px;
          color:white

        }
    }
</style>