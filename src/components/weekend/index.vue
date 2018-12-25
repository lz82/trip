<template>
  <div class="weekend-wrapper">
    <h3 class="title">
      周末去哪儿
    </h3>
    <ul class="list">
      <li class="item" v-for="item in list" :key="item.img">
        <div class="img-wrapper">
          <img :src="item.img" alt="">
        </div>
        <div class="content">
          <h4 class="item-title">{{item.title}}</h4>
          <p class="item-desc">
            {{item.desc}}
          </p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Weekend',

  data () {
    return {
      list: [{
        img: '//img1.qunarzz.com/sight/source/1511/ea/7f43191b747bb9.jpg_r_640x214_f58e829d.jpg',
        title: '上海去哪儿泡温泉',
        desc: '上海的朋友总会问，哪里可以泡温泉，哪里的温泉好呢'
      },
      {
        img: '//img1.qunarzz.com/sight/source/1509/41/0a74389a026adc.jpg_r_640x214_5ad7add7.jpg',
        title: '上海赏秋攻略',
        desc: '上海的秋天，哪里都是美美哒'
      },
      {
        img: '//img1.qunarzz.com/sight/source/1505/7d/df6ff468331c43.jpg_r_640x214_1f3783d0.jpg',
        title: '上海必游TOP10',
        desc: '中西合璧，现代和传统各有各的精彩'
      },
      {
        img: '//img1.qunarzz.com/sight/source/1603/ad/69b0fc5f48ad5f.jpg_r_640x214_b0fd5c7b.jpg',
        title: '亲子时光TOP榜',
        desc: '走进自然或玩转乐园，感知大千世界'
      }]
    }
  }
}
</script>

<style lang="less" scoped>
  .weekend-wrapper {
    overflow: hidden;
    .title {
      padding-left: 13px;
      text-align: left;
      font-size: 14px;
      line-height: 40px;
      box-sizing: border-box;
    }
    .list {
      background-color: #f5f5f5;
      .item {
        display: flex;
        flex-flow: column nowrap;
        align-items: flex-start;
        margin-bottom: 6px;
        &:last-child {
          margin-bottom: 0;
        }
        .img-wrapper {
          overflow: hidden;
          height: 0;
          padding-bottom: 37.43%;
          img {
            width: 100%;
          }
        }
        .content {
          width: 100%;
          background-color: #fff;
          .item-title {
          text-align: left;
          padding-top: 7px;
          padding-left: 13px;
          font-size: 14px;
          line-height: 24px;
        }
        .item-desc {
          text-align: left;
          width: 100%;
          box-sizing: border-box;
          padding: 0 70px 10px 13px;
          font-size: 12px;
          color: #616161;
          white-space: nowrap;
          text-overflow: ellipsis;
          overflow: hidden;
          text-indent: 0;
          line-height: 21px;
        }
        }
      }
    }
  }
</style>
