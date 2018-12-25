<template>
  <div class="hot-wrapper">
    <div class="header">
      <div class="left"><img src="//img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png" />本周热门榜单</div>
      <div class="right">全部榜单 ></div>
    </div>
    <div class="content-wrapper" ref="wrapper">
        <ul class="content" ref="content">
          <li v-for="(item, index) in list" :key="item.img" class="item">
            <div class="top" v-if="index === 0">
              <img src="//img1.qunarzz.com/piao/fusion/1710/ab/159673b63e6ca702.png" alt="">
            </div>
            <div class="top" v-if="index === 1">
              <img src="//img1.qunarzz.com/piao/fusion/1710/2d/36d0c4adaebbbc02.png" alt="">
            </div>
            <div class="top" v-if="index === 2">
              <img src="//img1.qunarzz.com/piao/fusion/1710/67/edc47ffef9e96b02.png" alt="">
            </div>
            <img :src="item.img" alt="">
            <div class="name">{{item.name}}</div>
            <div class="price-wrapper"><span class="price">￥{{item.price}}</span>起</div>
          </li>
        </ul>

    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: 'Hot',

  data () {
    return {
      scroll: null,
      list: [
        {
          name: '上海迪士尼乐园',
          price: 100,
          img: '//img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_250x250_57ac4faa.jpg'
        },
        {
          name: '上海欢乐谷',
          price: 150,
          img: '//img1.qunarzz.com/sight/p0/1811/e4/e4b9b471d2afc473a3.img.jpg_250x250_963fe222.jpg'
        },
        {
          name: '东方明珠',
          price: 148,
          img: '//img1.qunarzz.com/tuan/team2/1507/2c/83e0e0e7ae082a.jpg_250x250_87692c41.jpg'
        },
        {
          name: '上海野生动物园',
          price: 65,
          img: '//img1.qunarzz.com/sight/p0/1603/17/170481fb9caf500790.water.jpg_250x250_8c54e203.jpg'
        },
        {
          name: '上海动物园',
          price: 37,
          img: '//img1.qunarzz.com/sight/p0/1603/9b/9bf694a468dd774490.water.jpg_250x250_4c832079.jpg'
        },
        {
          name: '上海长风海洋世界',
          price: 85,
          img: '//img1.qunarzz.com/sight/p0/1802/b9/b995f17d885c97a4a3.water.jpg_250x250_cfbac125.jpg'
        }
      ]
    }
  },

  mounted () {
    let width = 24 + this.list.length * (100 + 6) - 6
    this.$refs.content.style.width = width + 'px'
    this.$nextTick(() => {
      this._initData()
    })
  },

  methods: {
    _initData () {
      this.scroll = new BScroll(this.$refs.wrapper, {
        scrollX: true,
        scrollY: false,
        click: true
      })
    }
  }
}
</script>

<style lang="less" scoped>
.hot-wrapper {
  background-color: #fff;
  .header {
    display: flex;
    flex-flow: row nowrap;
    box-sizing: border-box;
    justify-content: space-between;
    align-items: center;
    padding: 12px;
    .left {
      font-size: 16px;
      img {
        width: 15px;
        height: 15px;
        margin-right: 5px;
      }
    }
    .right {
      font-size: 12px;
      color: #616161;
    }
  }
  .content-wrapper {
    width: 100%;
    overflow: hidden;
    position: relative;
    .content {
      display: flex;
      box-sizing: border-box;
      flex-flow: row nowrap;
      padding: 0 12px;
      li {
        display: flex;
        flex-flow: column nowrap;
        padding: 3px 0 10px 0;
        font-size: 12px;
        margin-left: 6px;
        position: relative;
        &:first-child {
          margin-left: 0;
        }
        img {
          width: 100px;
          height: 100px;
          margin-bottom: 6px;
        }
        .price {
          color: #ff8300;
        }
        .top {
          width: 40px;
          height: 20px;
          position: absolute;
          left: 0;
          top: 0;
          img {
            width: 100%;
            height: 100%;
          }
        }
      }
    }
  }
}
</style>
