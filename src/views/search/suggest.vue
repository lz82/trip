<template>
  <div class="suggest-wrapper">
    <div class="title">
      <span>搜索建议</span>
      <span>关闭</span>
    </div>
    <div class="suggest-list">
      <div class="suggest" v-for="sug in suggestList" :key="sug.content">
        <span><img :src="sug.icon" alt=""></span>
        <span>{{sug.content}}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SearchSuggest',

  data () {
    return {
      suggestList: [{
        icon: 'http://img1.qunarzz.com/piao/fusion/1608/cf/7635983375250702.png',
        content: '搜索海南的全部景点1'
      },
      {
        icon: 'http://img1.qunarzz.com/piao/fusion/1608/58/d7b7b980b9bb4102.png',
        content: '金山卫城1'
      }, {
        icon: 'http://img1.qunarzz.com/piao/fusion/1608/cf/7635983375250702.png',
        content: '搜索海南的全部景点2'
      },
      {
        icon: 'http://img1.qunarzz.com/piao/fusion/1608/58/d7b7b980b9bb4102.png',
        content: '金山卫城2'
      }, {
        icon: 'http://img1.qunarzz.com/piao/fusion/1608/cf/7635983375250702.png',
        content: '搜索海南的全部景点3'
      },
      {
        icon: 'http://img1.qunarzz.com/piao/fusion/1608/58/d7b7b980b9bb4102.png',
        content: '金山卫城3'
      }]
    }
  },

  methods: {

  },

  mounted () {}
}
</script>

<style lang="less" scoped>
  .suggest-wrapper {
    .title {
      position: relative;
      line-height: 26px;
      padding: 0 10px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: space-between;
      &:after {
        position: absolute;
        left: 0;
        right: 0;
        bottom: 0;
        height: 1px;
        content: '';
        transform: translateY(50%);
        background-color: #dce5e7;
      }
    }
    .suggest-list {
      display: flex;
      flex-flow: column nowrap;
      background-color: #fff;
      .suggest {
        height: 41px;
        box-sizing: border-box;
        padding: 0 10px;
        display: flex;
        flex-flow: row nowrap;
        align-items: center;
        position: relative;
        &:after {
          content: '';
          position: absolute;
          left: 0;
          right: 0;
          bottom: 0;
          height: 1px;
          transform: translateY(50%);
          background-color: #dce5e7;
        }
        img {
          width: 15px;
          height: 15px;
          margin-right: 10px;
        }
      }
    }
  }
</style>
