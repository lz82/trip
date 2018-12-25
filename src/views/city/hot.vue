<template>
  <div class="hot-wrapper">
    <div class="title">
      热门城市
    </div>
    <div class="content">
      <div class="hot-city" v-for="city in hotList" :key="city">
        {{city}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityHot',

  data () {
    return {
      hotList: ['北京', '上海', '三亚', '香港', '杭州', '广州', '成都', '深圳', '苏州', '桂林', '西安', '厦门']
    }
  }
}
</script>

<style lang="less" scoped>
  .hot-wrapper {
    display: flex;
    flex-flow: column nowrap;
    .title {
      line-height: 36px;
      text-align: left;
      padding-left: 15px;
    }
    .content {
      display: flex;
      flex-flow: row wrap;
      background-color: #fff;
      .hot-city {
        flex: 0 0 33.33%;
        line-height: 45px;
        font-size: 16px;
        box-sizing: border-box;
        border-right: solid 1px #ddd;
        border-bottom: solid 1px #ddd;
        &:nth-child(3n) {
          border-right-width: 0;
        }
        &:nth-child(10) {
          border-bottom-width: 0;
        }
        &:nth-child(11) {
          border-bottom-width: 0;
        }
        &:nth-child(12) {
          border-bottom-width: 0;
        }
      }
    }
  }
</style>
