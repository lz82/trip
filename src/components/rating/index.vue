<template>
  <div class="rating-wrapper">
    <i class="iconfont icon-star-fill" v-for="item in rating" :key="item" />
  </div>
</template>

<script>
export default {
  name: 'Rating',

  props: {
    score: {
      type: Number
    }
  },

  data () {
    return {}
  },

  computed: {
    rating () {
      return Math.round(this.score)
    }
  }
}
</script>

<style lang="less" scoped>
.rating-wrapper {
  display: flex;
  width: 85px;
  height: 14px;
  justify-content: flex-start;
  align-items: center;
  .iconfont {
    color: rgb(254, 166, 42);
  }
}
</style>
