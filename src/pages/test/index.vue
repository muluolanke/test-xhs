<template>
  <view class="home-page">
    <!-- 发现页 -->
    <find-page class="find-content"></find-page>
  </view>
</template>

<script>
import findPage from './find/index.vue'
export default {
  name: 'homePage',
  components: {  findPage },
  data() {
    return {
      cardId: '',
      shareCommon: {},
      shareInfo: {},
      options: {},
    }
  },
  onReady() {
    
  },
  onLoad(option) {
  },
  async mounted() {
    
  },
  onPageScroll(res) {
  },
  onShareAppMessage() {
  },
  methods: {
    changeTsb(url, v) {
      uni.pageScrollTo({
        scrollTop: 0,
        duration: 0,
      })
      uni.redirectTo({
        url: url,
      })
      
    },
  },
}
</script>

<style lang="scss" scoped>
.home-page {
  background: #ffffff;
  padding-bottom: 102rpx;  
  &.bottomHeight {
    padding-bottom: 150rpx;
  }
  ::v-deep .u-tabbar__content__item-wrapper {
    align-items: center;
    justify-content: space-around;
  }
  //发现页
  .find-content {
    //品牌车型tabs蓝条样式
    ::v-deep .u-tabs__wrapper__nav__line {
      height: 4rpx !important;
      background: #00b0f0;
      z-index: 1;
      bottom: 0rpx;
    }
  }
  //我的页面样式
  .my-order {
    ::v-deep .u-cell__body--large {
      margin-top: 17rpx;
      margin-bottom: 17rpx;
    }
    ::v-deep .u-cell__title-text--large {
      margin-left: 12rpx;
    }
  }
}
</style>
