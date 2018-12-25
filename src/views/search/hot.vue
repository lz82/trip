<template>
  <div class="hot-wrapper">
    <div class="history-wrapper">
      <div class="title">
        <span>搜索历史</span>
        <span class="sync"><i class="iconfont icon-del"></i><span>清除</span></span>
      </div>
      <div class="history-list">
        <span class="history" v-for="his in history" :key="his">
          {{his}}
        </span>
      </div>
    </div>
    <div class="title">
      <span>热门搜索</span>
      <span class="sync"><i class="iconfont icon-sync"></i><span>换一批</span></span>
    </div>
    <div class="hot-area-wrapper">
      <div class="icon"></div>
      <div class="area-list">
        <div class="area" v-for="area in hotArea" :key="area">
          {{area}}
        </div>
      </div>
    </div>
    <div class="hot-city-wrapper">
      <div class="icon"></div>
      <div class="city-list">
        <div class="city" v-for="city in hotCity" :key="city">
          {{city}}
        </div>
      </div>
    </div>
    <div class="banner">
      <div class="container">
        搜索身边的景点
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HotSearch',

  data () {
    return {
      history: ['大牌景区年中大促', '迪士尼购票赠餐券'],
      hotArea: ['乌镇西栅', '上海植物园', '常州中华恐龙园', '乌镇', '上海世纪公园', '上海海昌海洋公园', '七宝古镇'],
      hotCity: ['哈尔滨', '酒泉', '厦门', '威海']
    }
  },

  methods: {

  },

  mounted () {}
}
</script>

<style lang="less" scoped>
  .history-list {
    display: flex;
    position: relative;
    background-color: #fff;
    flex-flow: row wrap;
    height: 64px;
    align-items: center;
    .history {
      flex: 0 0 auto;
      box-sizing: border-box;
      margin: 0 7.5px;
      border: solid 1px #c7ced4;
      padding: 5px;
    }
    &:before {
      position: absolute;
      content: '';
      top: 0;
      left: 0;
      right: 0;
      height: 1px;
      transform: translateY(50%);
      background-color: #c7ced4;
    }
    &:after {
      position: absolute;
      content: '';
      bottom: 0;
      left: 0;
      right: 0;
      height: 1px;
      transform: translateY(50%);
      background-color: #c7ced4;
    }
  }
  .hot-wrapper {
    .title {
      background-color: #f0f5f6;
      line-height: 36px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: space-between;
      padding: 0 10px;
      color: #999;
      .sync {
        color: #00afc7;
        .icon-sync, .icon-del {
          margin-right: 5px;
          font-weight: 500;
       }
      }
    }
    .hot-area-wrapper {
      height: 91px;
      display: flex;
      flex-flow: row nowrap;
      align-items: center;
      background-color: #fff;
      border-bottom: solid 1px #dce5e7;
      .icon {
        flex: 0 0 37px;
        height: 63px;
        background: url('//img1.qunarzz.com/piao/fusion/1511/da/8c3405b0e7d493f7.png') no-repeat center / 16px 16px;
        border-right: solid 1px #dce5e7;
      }
      .area-list {
        flex: 1 1 auto;
        display: flex;
        flex-flow: row wrap;
        .area {
          line-height: 33px;
          padding: 0 15px;
          position: relative;
          &:after {
            position: absolute;
            content: '';
            width: 1px;
            border-right: dashed 1px #dce5e7;
            transform: translateY(-50%);
            // transform: translate(50%);
            height: 18px;
            top: 50%;
            // transform: translateX(-50%);
            right: 0;
          }
        }
      }
    }
    .hot-city-wrapper {
      height: 47px;
      display: flex;
      flex-flow: row nowrap;
      align-items: center;
      background-color: #fff;
      border-bottom: solid 1px #dce5e7;
      .icon {
        flex: 0 0 37px;
        height: 31.5px;
        background: url('//img1.qunarzz.com/piao/fusion/1511/e8/d46972e07444bbf7.png') no-repeat center / 16px 16px;
        border-right: solid 1px #dce5e7;
      }
      .city-list {
        flex: 1 1 auto;
        display: flex;
        flex-flow: row nowrap;
        padding: 0 3px 0 0 ;
        .city {
          box-sizing: border-box;
          flex: 1 1 25%;
          line-height: 33px;
          padding: 0 15px;
          position: relative;
          &:after {
            position: absolute;
            content: '';
            width: 1px;
            border-right: dashed 1px #dce5e7;
            transform: translateY(-50%);
            // transform: translate(50%);
            height: 18px;
            top: 50%;
            // transform: translateX(-50%);
            right: 0;
          }
        }
      }
    }
    .banner {
      background-color: #fff;
      height: 58px;
      box-sizing: border-box;
      padding: 10px;
      box-shadow: 0 1px 3px 1px #c7ced4;;
      .container {
        display: flex;
        height: 100%;
        justify-content: center;
        align-items: center;
        border: solid 1px #dce5e7;
      }
    }
  }
</style>
