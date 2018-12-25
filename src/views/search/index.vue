<template>
  <div class="search-wrapper">
    <search-header v-model="keyword" @focus="onSearchFocus" @blur="onSearchBlur"/>
    <hot-search v-show="showHot && !keyword"/>
    <search-suggest v-show="showHot && keyword"/>
  </div>
</template>

<script>
import SearchHeader from './header'
import HotSearch from './hot'
import SearchSuggest from './suggest'

export default {
  name: 'Search',

  components: {
    SearchHeader,
    HotSearch,
    SearchSuggest
  },

  data () {
    return {
      keyword: '',
      showHot: false
    }
  },

  methods: {
    onSearchFocus () {
      this.showHot = true
    },

    onSearchBlur () {
      this.showHot = false
    }
  },

  mounted () {}
}
</script>

<style>

</style>
