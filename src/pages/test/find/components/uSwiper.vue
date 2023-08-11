<template>
  <view
    class="find-swiper"
    :style="{
      height: swiperHeight + 'px',
    }">
    <view
      v-if="swiperList && swiperList.length > 0"
      class="u-swiper"
      :style="{
        height: swiperHeight + 'px',
        borderRadius: 0,
      }">
      <swiper
        class="u-swiper__wrapper"
        :style="{
          height: swiperHeight + 'px',
        }"
        @change="changeSwiper"
		interval="3000"
        :circular="true"
        :autoplay="true">
        <swiper-item
          class="u-swiper__wrapper__item"
          v-for="(item, index) in swiperList"
          :key="index">
          <view class="u-swiper__wrapper__item__wrapper">
            <image
              v-if="isBeside(index)"
              class="image_kv u-swiper__wrapper__item__wrapper__image"
              mode="widthFix"
              :src="item.src"
              :data-name="item.name"
              :style="{
                width: '100%',
                height: swiperHeight + 'px',
                borderRadius: 0,
              }"
              @tap="toPage(index)"></image> 
            <view class="icon"
              ><u-loading-icon mode="circle"></u-loading-icon
            ></view>
          </view>
        </swiper-item>
      </swiper>
      <!-- <swiper-dot :list="swiperList" :current="current"></swiper-dot> -->
    </view>
  </view>
</template>

<script>
// import SwiperDot from '@/components/swiperDot'
export default {
  name: 'uSwiper',
  components: {  },
  props: { json: { type: Array }, carJson: { type: Array } },
  computed: {
    swiperList() {
      let arr = []
      if (this.json.length > 0) {
        this.json.forEach((item) => {
          if (item.class != '0') {
            arr.push({
              src: item.src,
              name: item.alt,
              href: item.href,
              style: item.style,
            })
          }
        })
      }
	  console.log(arr)
      return arr.length > 20 ? arr.slice(0, 20) : arr
    },
  },
  data() {
    return {
      current: 0,
      swiperHeight: parseInt(
        (1341 / 1125) * uni.getSystemInfoSync().screenWidth
      ), //初始时swiper的高度是0}
    }
  },
  mounted() {},
  methods: {
    isBeside(index) {
      const abs = Math.abs(index - this.current)
      const total = this.swiperList.length
      if (abs <= 1) {
        return true
      } else return abs == total - 1
    },
    changeSwiper(e) {
      this.current = e.detail.current
    },
    toPage() {
      const current = this.swiperList[this.current]
      if (current.href) {
        // 外链
        if (current.style === '1.1') {
          const url = encodeURIComponent(current.href)
          uni.navigateTo({
            url: `/pages/viewpage/index?url=${url}`,
          })
        }
        // 小程序内跳转
        else {
          uni.navigateTo({
            url: `/${current.href}`,
          })
        }
      }
    },
  },
  options: { styleIsolation: 'shared' },
}
</script>

<style lang="scss" scoped>
.find-swiper {
  position: relative;
  background: #f4f5f7;
  .image_kv {
    position: relative;
    z-index: 1;
  }
  .icon {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
}
</style>
