<template>
  <div class="header-wrapper">
    <i class="iconfont icon-left back" @click="onBack"></i>
    <div class="search-input-wrapper">
      <input
        class="search-input"
        type="text"
        placeholder="输入城市或景点"
        v-on="inputListener"
        v-model="searchKey"
      />
      <a v-show="value" class="del" @click="onDel"></a>
    </div>
    <a class="btn">搜索</a>
  </div>
</template>

<script>
export default {
  name: 'SearchHeader',

  props: {
    value: {
      type: [String, Number],
      required: false
    }
  },


  data () {
    return {
      searchKey: '',
      showDel: false
    }
  },

  methods: {
    onBack () {
      this.$router.push('/home')
    },

    onDel () {
      this.searchKey = ''
    }
  },

  computed: {
    inputListener () {
      const vm = this
      return Object.assign({},
      vm.$listeners,
      {
        input (e) {
            vm.$emit('input', e.target.value)
        }
      })
    }
  },

  watch: {
    searchKey (val) {
      this.$emit('input', val)
    }
  }
}
</script>

<style lang="less" scoped>
  .header-wrapper {
    display: flex;
    flex-flow: row nowrap;
    background-color: #fff;
    line-height: 44px;
    align-items: center;
    .back {
      flex: 0 0 44px;
    }
    .search-input-wrapper {
      flex: 1 1 auto;
      position: relative;
      .search-input {
        box-sizing: border-box;
        width: 100%;
        height: 30px;
        background-color: #f2f2f2;
        outline: 0 none;
        border: 0;
        border-radius: 15px;
        padding: 0 30px 0 20px;
        text-align: center;
        font-size: 14px;
      }
      .del {
        position: absolute;
        right: 10px;
        top: 13px;
        width: 20px;
        height: 20px;
        background:url('//img1.qunarzz.com/piao/fusion/1803/53/d259068b610c1d02.png') no-repeat center / 20px 20px;
      }
    }
    .btn {
      flex: 0 0 50px;
    }
  }
</style>
