<template>
  <div class="header-wrapper">
    <span v-show="isShowBack" class="back" @click="onBack"><i class="iconfont icon-left"></i></span>

    <div class="pic-cnt">
      <i class="iconfont icon-picture"></i>
      <span class="cnt">3</span>
    </div>

    <div class="title">
      上海杜莎夫人蜡像(AAAA景区)
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',

  data () {
    return {
      isShowBack: true
    }
  },

  methods: {
    onBack () {
      this.$router.push('/')
    },

    hideBack () {
      this.isShowBack = false
    },

    showBack () {
      this.isShowBack = true
    }
  }
}
</script>

<style lang="less" scoped>
  .header-wrapper {
    overflow: hidden;
    height: 0;
    padding-bottom: 55%;
    background: url('//img1.qunarzz.com/sight/p0/1704/c9/c936f3fccfc6d7eda3.img.jpg_600x330_1be7ea5e.jpg') no-repeat center / 100%;
    position: relative;
    .back {
      position: absolute;
      left: 5px;
      top: 5px;
      width: 36px;
      height: 36px;
      border-radius: 50%;
      background-color: rgba(0, 0, 0, 0.5);
      // opacity: 0.5;
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;
      .icon-left {
        color: #fff;
        font-weight: 700;
        opacity: 1;
      }
    }
    .pic-cnt {
      width: 60px;
      height: 20px;
      position: absolute;
      left: 10px;
      bottom: 36px;
      // background-color: #000;
      background-color: rgba(0, 0, 0, 0.5);
      // opacity: 0.5;
      border-radius: 10px;
      color: #fff;
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;
      i {
        font-size: 12px;
        margin-right: 5px;
        opacity: 1;
      }
      .cnt {
        opacity: 1;
      }
    }
    .title {
      position: absolute;
      left: 10px;
      bottom: 10px;
      font-size: 18px;
      color: #fff;
      font-weight: 700;
    }
  }
</style>
