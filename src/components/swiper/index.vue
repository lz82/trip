<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <template v-for="item in content">
        <swiper-slide :key="item.img">
          <!-- <a :href="item.url"> -->
            <img :src="item.img" alt="">
          <!-- </a> -->
        </swiper-slide>
      </template>
      <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
  </div>
</template>

<script>
// require styles
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  name: 'Swiper',

  components: {
    swiper,
    swiperSlide
  },

  props: {
    option: {
      type: Object
    },

    content: {
      type: Array
    }
  },

  data () {
    return {
      swiperOption: this.option || {
        autoplay: true,
        loop: true,
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  }
}
</script>

<style lang="less" scoped>
.wrapper {
  img {
    width: 100%;
  }
  /deep/ .swiper-pagination-bullet-active {
    background: #fff;;
  }
}
</style>
