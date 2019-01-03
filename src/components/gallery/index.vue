<template>
  <div class="gallery-wrapper" @click.self="onClick">
    <div class="container">
      <swiper :options="swiperOption">
         <swiper-slide v-for="pic in picList" :key="pic.url">
          <img class="pic" :src="pic.url" alt="">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  name: 'Gallery',

  components: {
    swiper,
    swiperSlide
  },

  props: {
    picList: {
      type: Array,
      required: true
    }
  },

  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },

  methods: {
    onClick () {
      this.$emit('click')
    }
  }
}
</script>

<style lang="less" scoped>
  .gallery-wrapper {
    .swiper-container {
      overflow: inherit;
    }
    position: fixed;
    background-color: rgba(0, 0, 0, 0.9);
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
    .container {
      width: 100%;
      height: 0;
      // // overflow: hidden;
      padding-bottom: 56%;
    }
    .swiper-container {
      // width: 100%;
      // height: 0;
      // // overflow: hidden;
      // padding-bottom: 70%;
      .pic {
        width: 100%;
        object-fit: cover;
      }
    }
    .swiper-pagination {
      color: #fff;
      bottom: -30px;
    }
  }
</style>
