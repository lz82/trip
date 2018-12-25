<template>
  <div class="nav-wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="page in pages" :key="page.img">
        <div class="icon-wrapper">
          <div class="icon" v-for="(icon, index) in page" :key="index">
            <img :src="icon.img" alt="">
            <div class="desc">{{icon.desc}}</div>
          </div>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  name: 'NavCom',

  components: {
    swiper,
    swiperSlide
  },

  props: {
    iconList: {
      type: Array,
      required: true
    }
  },

  data () {
    return {
      swiperOption: {
        loop: true,
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  },

  computed: {
    pages () {
      let pages = []
      this.iconList.forEach((icon, index) => {
        const pageIndex = Math.floor(index / 8)
        if (!pages[pageIndex]) {
          pages[pageIndex] = []
        }
        pages[pageIndex].push(icon)
      })
      return pages
    }
  }
}
</script>

<style lang="less" scoped>
.nav-wrapper {
  padding-top: 5px;
  background-color: #fff;
  .icon-wrapper {
    display: flex;
    flex-flow: wrap row;
    font-size: 14px;
    .icon {
      flex: 0 0 25%;
      box-sizing: border-box;
      display: flex;
      flex-flow: nowrap column;
      align-items: center;
      justify-content: center;
      padding-top: 5px;
      img {
        width: 55px;
        height: 55px;
      }
      .desc {
        padding-top: 5px;
      }
    }
  }
  /deep/ .swiper-container {
    padding-bottom: 30px;
  }

  /deep/ .swiper-pagination-bullet {
    width: 6px;
    height: 6px;
  }

  /deep/ .swiper-pagination-bullet-active {
  background: rgba(0,175,190,.8);
  }
}
</style>
