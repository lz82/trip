<template>
  <div class="alpha-wrapper">
    <div class="title">
      字母排序
    </div>
    <div class="content">
      <div class="word" v-for="alph in alphabet" :key="alph" @click="onAlphClick(alph)">
        {{alph}}
      </div>
    </div>
    <div class="city" v-for="city in cityList" :key="'city_' + city.key" :ref="'city_' + city.key">
      <div class="city-title">{{city.key}}</div>
      <div class="city-list">
        <div class="city-name" v-for="cityname in city.list" :key="'cityname_' + city.key + '_' + cityname">
          {{cityname}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Alphabet',

  data () {
    return {
      alphabet: [],
      cityList: []
    }
  },

  methods: {
    _initData () {
      Array.apply(null, { length: 26 }).forEach((item, index) => {
        const tempKey = String.fromCharCode(65 + index)
        this.alphabet.push(tempKey)
        this.cityList.push({
          key: tempKey,
          list: ['阿坝藏族羌族自治州', '阿克苏地区', '阿拉尔', '阿拉善盟', '阿勒泰', '阿里', '安康', '安庆', '安顺', '安阳']
        })
      })
    },

    onAlphClick (key) {
      this.$emit('move', key)
    }
  },

  mounted () {
    this.$nextTick(() => {
      this._initData()
    })
  }
}
</script>

<style lang="less" scoped>
.alpha-wrapper {
  display: flex;
  flex-flow: column nowrap;
  .title {
    line-height: 36px;
    padding: 0 15px;
    text-align: left;
  }
  .content {
    background-color: #fff;
    display: flex;
    flex-flow: row wrap;
    .word {
      flex: 0 0 16.66%;
      line-height: 45px;
      color: #212121;
      font-weight: 500;
    }
  }
  .city {
    .city-title {
      line-height: 36px;
      padding: 0 15px;
      text-align: left;
    }
    .city-list {
      background-color: #fff;
      display: flex;
      flex-flow: row wrap;
      position: relative;
      &:after {
        position: absolute;
        left: 0;
        bottom: 0;
        right: 0;
        content: '';
        height: 1px;
        background-color: #fff;
      }
      .city-name {
        flex: 0 0 25%;
        box-sizing: border-box;
        line-height: 45px;
        border-right: solid 1px #ddd;
        &:nth-child(4n) {
          border-right-width: 0;
        }
        position: relative;
        &:after {
          position: absolute;
          content: '';
          left: 0;
          bottom: 0;
          right: 0;
          height: 1px;
          background-color: #ddd;
        }
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
      }
    }
  }
}
</style>
