header<template>
  <div class="detail-wrapper">
    <div class="fix-header" ref="header">
      <router-link tag="span" to="/" class="back"><i class="iconfont icon-left"></i></router-link>
      <span class="title">上海杜莎夫人蜡像馆</span>
    </div>

    <detail-header ref="detailheader" @click.native="onHeaderClick" />

    <gallery class="gallery" v-show="showGallery" :pic-list="gallery" @click="onGalleryClick" />

    <div class="intro">
      <div class="top">
        <div class="score">
          <div class="total"><span><span class="number">4.9</span>分</span><span>很棒</span></div>
          <div class="detail"><span>21771条评论</span><span>23条攻略</span></div>
        </div>
        <div class="info">
          <div class="title">景点介绍</div>
          <div class="detail">开放时间、贴士</div>
        </div>
      </div>
      <div class="location"><i></i>上海市黄浦区南京西路2-68号新世界商厦10楼</div>
    </div>

    <dl class="recommond">
      <dt>去哪儿推荐</dt>
      <dd v-for="item in recommondList" :key="item.id">
        <div class="left">
          <div class="name">{{item.name}}</div>
          <div class="time">{{item.time}}</div>
          <div class="tags">
            <span class="tag" v-for="tag in item.tags" :key="tag.text"><img :src="tag.icon" />{{tag.text}}</span>
          </div>
        </div>
        <div class="right">
          <div class="price"><span class="symbol">￥</span>{{item.price}}</div>
          <span class="btn">预定</span>
        </div>
      </dd>
    </dl>

    <div class="tab-wrapper">
      <ul class="tabbar" :class="{fixed: showTabbar}" ref="tabbar">
        <li v-for="tab in tabs" :class="{active: selectedTab === tab.val}" :key="tab.val" @click="onTabClick(tab.val)">{{tab.text}}</li>
      </ul>
    </div>

    <section ref="ticketwrapper">
    <dl class="ticket" v-for="ticket in ticketsList" :key="ticket.title">
      <dt><span class="icon"></span>{{ticket.title}}</dt>
      <dd v-for="item in ticket.categorys" :key="item.name">
        <div class="name">{{item.name}}</div>
        <div class="price"><span>￥</span><span class="num">{{item.price}}</span><span class="word">起</span></div>
      </dd>
    </dl>

    <dl class="ticket" v-for="ticket in oneDayList" :key="ticket.title">
      <dt><span class="icon icon-ticket"></span>{{ticket.title}}</dt>
      <dd v-for="item in ticket.categorys" :key="item.name">
        <div class="name">{{item.name}}</div>
        <div class="price"><span>￥</span><span class="num">{{item.price}}</span><span class="word">起</span></div>
      </dd>
    </dl>

    <dl class="ticket" v-for="ticket in hotList" :key="ticket.title">
      <dt><span class="icon"></span>{{ticket.title}}</dt>
      <dd v-for="item in ticket.categorys" :key="item.name">
        <div class="name">{{item.name}}</div>
        <div class="price"><span>￥</span><span class="num">{{item.price}}</span><span class="word">起</span></div>
      </dd>
    </dl>
    </section>
    <div style="width: 100%; height: 800px;"></div>
  </div>
</template>

<script>
import DetailHeader from './header'
import Gallery from '@/components/gallery'

export default {
  name: 'Detail',

  components: {
    DetailHeader,
    Gallery
  },

  props: {
    id: {
      type: [String, Number],
      required: true
    }
  },

  data () {
    return {
      gallery: [
        {
          url: '//img1.qunarzz.com/sight/p0/1704/c9/c936f3fccfc6d7eda3.img.jpg_r_800x800_93bf62f1.jpg'
        },
        {
          url: '//img1.qunarzz.com/sight/p0/1703/22/2244eaab209bf750a3.img.jpg_r_800x800_d4d9e847.jpg'
        },
        {
          url: '//img1.qunarzz.com/sight/p0/1709/fb/fb5f50e934a895bea3.water.jpg_r_800x800_30584971.jpg'
        },
        {
          url: '//img1.qunarzz.com/sight/p0/1704/74/74a3ba6334dd7cfa3.img.jpg_r_800x800_c2612186.jpg'
        }
      ],
      showGallery: false,
      showTabbar: false,
      recommondList: [
        {
          id: 1,
          name: '上海杜莎夫人蜡像馆成人票',
          time: '可订明日',
          tags: [{
            icon: 'https://img1.qunarzz.com/piao/fusion/1804/b0/c3cf2897c74ecc02.png',
            text: '自营'
          }, {
            icon: '',
            text: '随时退'
          }],
          price: 170
        },
        {
          id: 2,
          name: '上海杜莎夫人蜡像馆儿童票',
          time: '可订明日',
          tags: [{
            icon: 'https://img1.qunarzz.com/piao/fusion/1804/b0/c3cf2897c74ecc02.png',
            text: '自营'
          }, {
            icon: '',
            text: '随时退'
          }],
          price: 170
        },
        {
          id: 3,
          name: '上海杜莎夫人蜡像馆学生票',
          time: '可订明日',
          tags: [{
            icon: 'https://img1.qunarzz.com/piao/fusion/1804/b0/c3cf2897c74ecc02.png',
            text: '自营'
          }, {
            icon: '',
            text: '随时退'
          }],
          price: 170
        }
      ],
      tabs: [{
        val: 'ticket',
        text: '门票'
      }, {
        val: 'oneday',
        text: '一日游'
      }, {
        val: 'hot',
        text: '热销组合'
      }],
      selectedTab: 'ticket',
      ticketsList: [{
        title: '特价票',
        type: 'ticket',
        categorys: [
          {
            name: '上海杜莎夫人蜡像馆双人票',
            price: 288
          },
          {
            name: '上海杜莎夫人蜡像馆成人票+蛋糕+咖啡优惠券',
            price: 190
          }
        ]
      },
      {
        title: '门票（电子票）',
        type: 'ticket',
        categorys: [
          {
            name: '杜莎夫人蜡像馆成人票',
            price: 164.8
          },
          {
            name: '杜莎夫人蜡像馆学生票',
            price: 129.9
          },
          {
            name: '杜莎夫人蜡像馆儿童票',
            price: 129.9
          },
          {
            name: '杜莎夫人蜡像馆亲子票（1大1小）',
            price: 300
          }
        ]
      },
      {
        title: '门票（统一入园）',
        type: 'ticket',
        categorys: [
          {
            name: '杜莎夫人蜡像馆+黄浦江游览成人票（统一入园）',
            price: 198
          }
        ]
      }],
      oneDayList: [{
        title: '一日游',
        type: 'trip',
        categorys: [
          {
            name: '【上海出发】东方明珠+上海杜莎夫人蜡像馆+上海历史发展陈列馆+黄浦江浏览+城隍庙旅游区1日游',
            price: 288
          },
          {
            name: '【上海出发】东方明珠+外滩+上海杜莎夫人蜡像馆+上海历史发展陈列馆+黄浦江浏览+城隍庙旅游区1日游',
            price: 308
          }
        ]
      }],
      hotList: [{
        title: '热销联票',
        type: 'ticket',
        categorys: [
          {
            name: '长风海洋世界+杜莎蜡像馆成人联票',
            price: 140
          },
          {
            name: '长风海洋世界+杜莎蜡像馆儿童联票',
            price: 220
          },
          {
            name: '东方明珠+杜莎蜡像馆成人联票',
            price: 235
          },
          {
            name: '东方明珠+浦江游船+杜莎蜡像馆成人联票',
            price: 339
          },
          {
            name: '长风海洋世界+杜莎蜡像馆儿童联票+乐高探索中心三馆成人联票',
            price: 360
          }
        ]
      }]
    }
  },

  created () {
    window.addEventListener('scroll', this.scrollHandler)
  },

  beforeDestroy () {
    window.removeEventListener('scroll', this.scrollHandler)
  },

  mounted () {
  },

  methods: {
    onHeaderClick () {
      this.showGallery = true
    },

    onGalleryClick () {
      this.showGallery = false
    },

    scrollHandler () {
      const top = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
      const header = this.$refs.header
      header.style.opacity = (top / 44) > 1 ? 1 : (top / 44)
      if (top > 0) {
        this.$refs.detailheader.hideBack()
      } else {
        this.$refs.detailheader.showBack()
      }
      const wrapper = this.$refs.ticketwrapper
      const wrapperOffset = wrapper.offsetTop
      const offset = wrapperOffset - top
      if (offset < 54) {
        if (offset > (120 - wrapper.offsetHeight)) {
          this.showTabbar = true
        } else {
          this.showTabbar = false
        }
      } else {
        this.showTabbar = false
      }
    },

    onTabClick (tab) {
      this.selectedTab = tab
    }
  }
}
</script>

<style lang="less" scoped>
  .detail-wrapper {
    .gallery {
      z-index: 20;
    }
    .fix-header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      line-height: 44px;
      z-index: 1;
      background-color: #00bcd4;
      color: #fff;
      font-size: 16px;
      font-weight: 700;
      opacity: 0;
      .back {
        position: absolute;
        left: 10px;
      }
    }
    .intro {
      display: flex;
      flex-flow: column nowrap;
      height: 100px;
      box-sizing: border-box;
      padding: 5px 10px 0;
      position: relative;
      top: -5px;
      background-color: #fff;
      border-radius: 5px 5px 0 0 ;
      .top {
        display: flex;
        flex-flow: row nowrap;
        height: 56px;
        box-sizing: border-box;
        align-items: center;
        .score {
          position: relative;
          flex: 0 0 50%;
          display: flex;
          flex-flow: column nowrap;
          justify-content: center;
          align-items: flex-start;
          &:before {
            content: '';
            position: absolute;
            top: 5px;
            right: 0;
            bottom: 5px;
            width: 1px;
            background-color: rgb(224, 224, 224);
            transform: scaleX(0.333)
          }
          &:after {
            content: "\e7ec";
            font-family:"iconfont" !important;
            font-size:16px;
            font-style:normal;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            position: absolute;
            right: 10px;
            top: 50%;
            transform: translateY(-50%);
            color: #9e9e9e;
          }
          .total {
            line-height: 25px;
            color: #ff8300;
            font-weight: 500;
            .number {
              font-size: 22px;
              margin-right: 10px;
            }
          }
          .detail {
            color: #9e9e9e;
            font-size: 12px;
            span:first-child {
              margin-right: 10px;
            }
          }
        }
        .info {
          flex: 0 0 50%;
          line-height: 41px;
          height: 41px;
          box-sizing: border-box;
          display: flex;
          position: relative;
          flex-flow: column nowrap;
          justify-content: center;
          align-items: flex-start;
          padding-left: 15px;
          &:after {
            content: "\e7ec";
            font-family:"iconfont" !important;
            font-size:16px;
            font-style:normal;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            position: absolute;
            right: 10px;
            top: 50%;
            transform: translateY(-50%);
            color: #9e9e9e;
          }
          .title {
            line-height: 24px;
            font-size: 14px;
            color: #212121;
          }
          .detail {
            line-height: 14px;
            font-size: 12px;
            color: #9e9e9e;
          }
        }
      }
      .location {
        line-height: 38px;
        display: flex;
        flex-flow: row nowrap;
        justify-content: flex-start;
        padding: 0 28px;
        position: relative;
        font-size: 14px;
        color: #212121;
        &:before {
          content: "\e790";
          font-family:"iconfont" !important;
          font-size:16px;
          font-style:normal;
          -webkit-font-smoothing: antialiased;
          -moz-osx-font-smoothing: grayscale;
          position: absolute;
          left: 6px;
          color: #9e9e9e;
        }
        &:after {
          content: "\e7ec";
          font-family:"iconfont" !important;
          font-size:16px;
          font-style:normal;
          -webkit-font-smoothing: antialiased;
          -moz-osx-font-smoothing: grayscale;
          position: absolute;
          right: 6px;
          color: #9e9e9e;
        }
      }
    }

    .recommond {
      margin: 10px 0;
      background-color: #fff;
      display: flex;
      flex-flow: column nowrap;
      align-items: flex-start;
      padding-left: 10px;
      dt {
        box-sizing: border-box;
        line-height: 44px;
        width: 100%;
        position: relative;
        text-align: left;
        padding: 0 10px;
        background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAMAAABg3Am1AAAAflBMVEUAAAD/bm7/b2//b2//eXn/b2//b2//bm7/b2//b2//bm7/b2//b2//b2//bm7/b2//b2//cXH/eHj/qqr/bm7/////cXH/iIj/oqL//f3/mJj/fHz/9/f/8PD/4eH/ycn/6+v/1dX/0ND/t7f/ra3/kpL/jo7/c3P/5ub/vr7o37bEAAAAFHRSTlMA9uZeCfny7NvLt6+PfGZONxsRA/pz1k8AAAFrSURBVEjHpZbZdoMwDERtMEvYE8YJZN/b/v8PNvicJsiYqJzcB548WGNZksUAVWZJHAVBFCdZqQTDwk8lesjUX4hxVB5iQJiPbVMXHpx4RS0czGcYZTYXAyoPb/AqYeFLvEX61nqwEEUlwSKrnl9X/JtmZfl4Oq9d53Pfan2yzurvdAs42OsHaxAKYVDOA207wcEKShlBDhfaIUBu7lsIl2UjuIASLkZTsDaCxpWMFC7ORrCBRfqw7MxZY9Z/w0YqUWLI8tLqJ+25n8BSZP3Am+aG2/Vw1IQ9XmQiwZNV9z+0mkKtJCKmAg094IgXsYg4Ab0gkQh4wRUvgv8I1kTAh7QHCYk3fQIxnbCCHXokImMFPyCJKznB9gvkaijJ7XCnl0+kU3ZISQFttp3DnWW5oQVES3S57D4Eq0RJE+DJSZvh8RRpZDwFaZU8s5o0YxZvPrXdTx0on40sfih+Nnb5wT7x6fDR42Ty8+cXnHyOvDgQEbUAAAAASUVORK5CYII=) no-repeat left center / 18px 18px;
        text-indent: 18px;
        font-size: 16px;
        &:after {
          content: '';
          position: absolute;
          left: 0;
          right: 0;
          bottom: 0;
          height: 1px;
          background-color: rgb(218, 218, 218);
          transform: scaleY(0.333333)
        }
      }
      dd {
        position: relative;
        width: 100%;
        box-sizing: border-box;
        display: flex;
        flex-flow: row nowrap;
        justify-content: space-between;
        padding: 10px 10px 12px 0;
        &:after {
          content: '';
          position: absolute;
          left: 0;
          right: 0;
          bottom: 0;
          height: 1px;
          background-color: rgb(218, 218, 218);
          transform: scaleY(0.333333)
        }
        &:last-child:after {
          height: 0;
        }
        .left {
          display: flex;
          flex-flow: column nowrap;
          align-items: flex-start;
          flex: 1 1 auto;
          .name {
            font-size: 15px;
            line-height: 26px;
            font-weight: 400;
          }
          .time {
            line-height: 16px;
            font-size: 12px;
            color: #616161;
            background: url(https://img1.qunarzz.com/piao/fusion/1804/25/792e9929973a9902.png) no-repeat left center / 10px 11px;
            text-indent: 11px;
          }
          .tags {
            display: flex;
            flex-flow: row wrap;
            min-height: 20px;
            align-items: center;
            .tag {
              display: inline-block;
              border: solid 1px #a5e4ec;
              border-radius: 3px;
              line-height: 16px;
              height: 16px;
              box-sizing: border-box;
              font-size: 10px;
              color: #00afc7;
              margin-right: 5px;
              padding: 1px;
              img {
                height: 8px;
                margin-right: 2px;
              }
            }
          }
        }
        .right {
          display: flex;
          flex-flow: column nowrap;
          justify-content: center;
          color: #ff9800;
          .price {
            .symbol {
              font-size: 12px;
            }
            font-size: 20px;
            font-weight: 500;
          }
          .btn {
            height: 30px;
            line-height: 30px;
            background-image: linear-gradient(130deg,#ffab1e 37%,#ff8c12 100%);
            color: #fff;
            width: 90px;
            font-size: 14px;
            font-weight: 500;
            border-radius: 5px;
          }
        }

      }
    }
    .tab-wrapper {
      width: 100%;
      height: 44px;
      .tabbar {
        display: flex;
        flex-flow: row nowrap;
        background-color: #fff;
        justify-content: space-around;
        align-items: center;
        height: 46px;
        box-sizing: border-box;
        font-size: 16px;
        color: #212121;
        position: relative;
        &.fixed {
          position: fixed;
          top: 44px;
          left: 0;
          right: 0;
          z-index: 1;
        }
        &:after {
          content: '';
          position: absolute;
          left: 0;
          right: 0;
          bottom: 0;
          height: 1px;
          transform: scaleY(0.5);
          background-color: #e0e0e0;
        }
        li {
          flex: 0 0 33%;
          position: relative;
          line-height: 46px;
          box-sizing: border-box;
          &.active:after {
            content: '';
            position: absolute;
            left: 0;
            right: 0;
            width: 50%;
            left: 50%;
            transform: translateX(-50%);
            bottom: 0;
            height: 2px;
            background-color: #00bcd4;
          }
        }
      }
    }
    .ticket {
      margin-bottom: 10px;
      background-color: #fff;
      display: flex;
      flex-flow: column nowrap;
      align-items: flex-start;
      padding: 0 10px;
      box-sizing: border-box;
      dt {
        display: flex;
        flex-flow: row nowrap;
        justify-content: left;
        align-items: center;
        box-sizing: border-box;
        width: 100%;
        font-size: 14px;
        .icon {
          display: inline-block;
          width: 18px;
          height: 18px;
          background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) no-repeat;
          background-position-x: 0;
          background-size: 20px 150px;
          &.icon-ticket {
            background-position-y: -22.5px;
          }
        }
        line-height: 44px;
        text-indent: 2px;
        position: relative;
        &:after {
          content: '';
          position: absolute;
          left: 0;
          right: 0;
          bottom: 0;
          height: 1px;
          background-color: rgb(218, 218, 218);
          transform: scaleY(0.333333)
        }
      }
      dd {
        box-sizing: border-box;
        width: 100%;
        // line-height: 48px;
        padding: 12px 0;
        display: flex;
        flex-flow: row nowrap;
        justify-content: space-between;
        position: relative;
        font-size: 14px;
        &:after {
          position: absolute;
          content: '';
          left: 0;
          right: 0;
          bottom: 0;
          height: 1px;
          background-color: #dadada;
          transform: scaleY(0.5);
        }
        &:last-child:after {
          height: 0;
        }
        .name {
          flex: 1 1 auto;
          text-align: left;
          // display: flex;
          // flex-direction: column;
          // // display: flex;
          // // flex-flow: column wrap;
          // overflow: hidden;
          // text-overflow: ellipsis;
          // -webkit-line-clamp: 2;
          overflow: hidden;
            text-overflow: ellipsis;
            display: -webkit-box;
            -webkit-line-clamp:2;
            -webkit-box-orient: vertical;
            line-height: 24px;
        }
        .price {
          flex: 0 0 120px;
          text-align: right;
          display: flex;
          flex-flow: row nowrap;
          justify-content: center;
          align-items: center;
          font-size: 12px;
          color: #ff9800;
          .num {
            font-size: 20px;
            font-weight: 700;
          }
          .word {
            color: #9e9e9e;
          }
        }
      }
    }
  }
</style>
