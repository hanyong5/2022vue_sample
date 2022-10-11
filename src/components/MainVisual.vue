<template>
  <div class="visual">
    <Swiper >
      <swiper-slide class="item">test1</swiper-slide>
      <swiper-slide class="item">test2</swiper-slide>
      <swiper-slide class="item">test3</swiper-slide>
    </Swiper>
  </div>
</template>

<script>
import {Swiper,SwiperSlide} from "swiper/vue";
import "swiper/css"
export default {
  components:{
    Swiper,
    SwiperSlide,
  }
}
</script>

<style lang="scss">
    .visual{
        background: pink;
        margin-bottom: 20px;
        .item{
          height: 300px;
          display: flex;
          justify-content: center;
          align-items: center;
        }
    }
</style>