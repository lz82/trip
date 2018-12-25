<template>
  <div class="wrapper">
    <header-com />

    <swiper class="swiper" :content="swiperList" />

    <nav-com :icon-list="iconList"/>

    <toplink class="mb10" />

    <banner class="mb10" />

    <hot class="mb10" />

    <guess class="mb10" />

    <weekend class="mb10" />

    <bottom-com class="mb10" />
  </div>
</template>

<script>
// import VConsole from 'vconsole'
import headerCom from '@/components/header'
import swiper from '@/components/swiper'
import navCom from '@/components/nav'
import toplink from '@/components/toplink'
import banner from '@/components/banner'
import hot from '@/components/hot'
import guess from '@/components/guess'
import weekend from '@/components/weekend'
import bottomCom from '@/components/bottom'

export default {
  name: 'Home',

  components: {
    headerCom,
    swiper,
    navCom,
    toplink,
    banner,
    hot,
    guess,
    weekend,
    bottomCom
  },

  data () {
    return {
      swiperList: [{
        img: 'http://img1.qunarzz.com/piao/fusion/1811/c6/2467595fffc3b302.jpg_750x200_bc88db3a.jpg',
        url: '/home'
      },
      {
        img: 'http://img1.qunarzz.com/piao/fusion/1810/af/30ffcf34e9819f02.jpg_750x200_736b7236.jpg',
        url: '/home'
      },
      {
        img: 'http://img1.qunarzz.com/piao/fusion/1811/7c/8e5c4ab8ee8b7402.jpg_750x200_dd7a38dd.jpg',
        url: '/home'
      }],

      iconList: [
        {
          img: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          url: '/home',
          desc: '景点门票'
        },
        {
          img: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          url: '/home',
          desc: '一日游'
        },
        {
          img: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          url: '/home',
          desc: '上海必游'
        },
        {
          img: 'https://img1.qunarzz.com/piao/fusion/1810/50/26ffa31b56646402.png',
          url: '/home',
          desc: '上海海昌'
        },
        {
          img: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          url: '/home',
          desc: '打卡圣地'
        },
        {
          img: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
          url: '/home',
          desc: '泡温泉'
        },
        {
          img: 'http://img1.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png',
          url: '/home',
          desc: '上海欢乐谷'
        },
        {
          img: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
          url: '/home',
          desc: '野生动物园'
        },
        {
          img: 'http://img1.qunarzz.com/piao/fusion/1803/de/f26be47a6bf02a02.png',
          url: '/home',
          desc: '上海迪士尼'
        },
        {
          img: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
          url: '/home',
          desc: '全部玩乐'
        }
      ]
    }
  },

  mounted () {
    // console.log('home page mounted...')
    /* eslint-disable-next-line */
      // const vConsole = new VConsole()
  },

  methods: {

  }
}
</script>

<style lang="less" scoped>
.wrapper {
  .swiper {
    height: 0;
    overflow: hidden;
    padding-bottom: 26.67%;
  }
  .mb10 {
    margin-bottom: 10px;
  }
}
</style>
