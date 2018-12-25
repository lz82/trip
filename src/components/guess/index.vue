<template>
  <div class="guess-wrapper">
    <h5 class="title">
      <img src="//img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt=""><span>猜你喜欢</span>
    </h5>
    <ul class="list">
      <li class="item" v-for="item in list" :key="item.img">
        <div class="left">
          <div class="can-order" v-if="item.canOrder">
            可订明日
          </div>
          <div class="img">
            <img :src="item.img" alt="">
          </div>
        </div>
        <div class="right">
          <h5 class="item-title">{{item.name}}</h5>
          <div class="rating">
            <rating :score="item.rating" />
            <span class="review">{{item.reviewCnt}}条评论</span>
          </div>
          <div class="price">
            <div class="price-left">
              <span class="curreny">¥</span><span class="number">{{item.price}}</span><span class="desc">起</span>
            </div>
            <div class="price-right">
              <span class="area">{{item.area}}</span>
            </div>
          </div>
          <div class="item-desc">
            <span>{{item.desc}}</span>
          </div>
        </div>
      </li>
    </ul>
    <div class="more">
      查看所有产品
    </div>
  </div>
</template>

<script>
import rating from '@/components/rating'

export default {
  name: 'Guess',

  components: {
    rating
  },

  data () {
    return {
      list: [
        {
          name: '上海杜莎夫人蜡像馆',
          img: '//img1.qunarzz.com/sight/p0/1704/c9/c936f3fccfc6d7eda3.img.jpg_200x200_46052773.jpg',
          canOrder: 1,
          rating: 4.9,
          reviewCnt: 21303,
          price: 130,
          area: '黄浦区',
          desc: '听说吴亦凡喔skr'
        },
        {
          name: '上海欢乐谷',
          img: '//img1.qunarzz.com/sight/p0/1811/e4/e4b9b471d2afc473a3.img.jpg_200x200_9a7794fc.jpg',
          canOrder: 1,
          rating: 4.9,
          reviewCnt: 33144,
          price: 150,
          area: '松江区',
          desc: '敢上1200米长的木质过山车吗？'
        },
        {
          name: '上海迪士尼乐园',
          img: '//img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          canOrder: 1,
          rating: 4.8,
          reviewCnt: 205306,
          price: 100,
          area: '浦东新区',
          desc: '全球最大的迪士尼城堡'
        },
        {
          name: '上海马戏城',
          img: '//img1.qunarzz.com/sight/p0/1503/36/36a266a141bccdc9.water.jpg_200x200_069fe6d8.jpg',
          canOrder: 1,
          rating: 4.8,
          reviewCnt: 1721,
          price: 361,
          area: '闸北区',
          desc: '上海国际文化都市的标志性建筑'
        },
        {
          name: '上海动物园',
          img: '//img1.qunarzz.com/sight/p0/1603/9b/9bf694a468dd774490.water.jpg_200x200_c7f8a6ad.jpg',
          canOrder: 1,
          rating: 4.8,
          reviewCnt: 13013,
          price: 35.1,
          area: '长宁区',
          desc: '巨型象龟了解一下~'
        },
        {
          name: '上海中心大厦',
          img: '//img1.qunarzz.com/sight/p0/1707/62/62981f052681ef5ba3.img.jpg_200x200_43d6d1e7.jpg',
          canOrder: 0,
          rating: 4.4,
          reviewCnt: 7563,
          price: 90,
          area: '浦东新区'
        }
      ]
    }
  }
}
</script>

<style lang="less" scoped>
.guess-wrapper {
  background-color: #fff;
  display: flex;
  flex-flow: column nowrap;
  .title {
    display: flex;
    flex-flow: row nowrap;
    justify-content: flex-start;
    align-items: center;
    box-sizing: border-box;
    padding: 12px;
    font-size: 14px;
    img {
      width: 15px;
      height: 15px;
      margin-right: 5px;
    }
  }
  .list {
    margin-left: 12px;
    .item {
      display: flex;
      flex-flow: row nowrap;
      padding: 10px 0;
      position: relative;
      &:not(:last-child):after {
        position: absolute;
        content: ' ';
        width: 100%;
        height: 1px;
        background-color: rgb(224, 224, 224);
        transform: scaleY(0.5);
        left: 0;
        bottom: 5px;
      }
      .left {
        flex: 0 0 100px;
        position: relative;
        .can-order {
          display: flex;
          flex-flow: row nowrap;
          justify-content: center;
          align-items: center;
          width: 51px;
          height: 19px;
          font-size: 10px;
          background:url(https://img1.qunarzz.com/piao/fusion/1802/52/b9080e45b69b4f02.png) left ;
          background-size: 100%;
          color: #fff;
          position: absolute;
          top: 0;
          left: 0;
        }
        .img {
          width: 100px;
          height: 100px;
          img {
            width: 100%;
            height: 100%;
          }
        }
      }
      .right {
        margin-left: 12px;
        padding-right: 12px;
        display: flex;
        flex-flow: column nowrap;
        flex: 1 1 auto;
        .item-title {
          font-size: 16px;
          padding-top: 13px;
          text-align: left;
        }
        .rating {
          display: flex;
          align-items: center;
          padding-top: 7px;
          .review {
            color: #616161;
            font-size: 12px;
          }
        }
        .price {
          display: flex;
          flex-flow: row nowrap;
          justify-content: space-between;
          align-items: flex-end;
          padding-top: 11px;
          .price-left {
            .curreny {
              color: #ff8300;
              font-size: 12px;
            }
            .number {
              color: #ff8300;
              font-size: 20px;
            }
          }
        }

        .item-desc {
          display: inline-block;
          overflow: hidden;
          margin-top: 24px;
          padding: 2px 5px;
          text-align: left;
          color: #f55;
          span {
            background-color: #fff9f9;
          }
        }
      }
    }
  }
  .more {
    padding: 10px 0;
    color: #00afc7;
    font-size: 14px;
    position: relative;
    &:before {
      content: '';
      position: absolute;
      background-color: rgb(224, 224, 224);
      top: 0;
      left: 0;
      width: 100%;
      height: 1px;
      transform: scaleY(0.5)
    }
  }
}
</style>
