<template>
  <view class="find-content">
    <!--置顶按钮-->
    <!-- <view
    class="top-button container"
    :style="{ opacity: tabsWhite ? opacity : 0, paddingTop: navTop + 'px',display: tabsWhite?'flex':'none' }">
    <image
      class="logo"
      src="https://brand2.svw-volkswagen.com/cms/prod/I/20230804/f09554dd2d5b39f04636dd31b782aab3.jpg"
      mode="heightFix"></image>
    <view class="btn-list">
      <view
        class="btnb"
        v-for="(item, index) in buttonList"
        :key="index"
        @click="toHref(item.href)"
        :data-name="`发现-顶栏-${item.value}`"
        :class="{ pinjian: index == 1 }">
        {{ item.value }}
      </view>
    </view>
  </view> -->
    <!-- 轮播 -->
    <u-swiper  :json="kvJson" interval="3000" :carJson="brandJson.listBrand"></u-swiper>
    <!-- 精彩活动 -->
    <view class="container activity">
      <view class="title">精彩活动</view>
      <template v-for="(item, i) in marveList">
        <view v-if="item.item.class != '0'" class="list-box" :key="i">
          <image
            :data-name="item.item.hrefParamSc"
            @click="toPage(item)"
            class="img"
            :src="item.item.src"
            mode="widthFix" />
          <view class="alt">{{ item.item.alt }}</view>
          <view class="desc">{{ item.item.hrefParamMz }}</view>
          <view
            class="btn"
            :data-name="`发现-精彩活动-${item.item.alt}`"
            @click="toPage(item)">
            {{ item.item.floatItems[0].value }}
          </view>
        </view>
      </template>
    </view>
  </view>
</template>
 
<script> 
import uSwiper from './components/uSwiper.vue'
// import { getHomeData ,getTest} from '@/api'
export default {
  name: 'findPage',
  components: {  uSwiper },
  data() {
    return {
      json: false,
      kvJson: [
    {
        "hrefParamSc": "朗逸领先版",
        "isshow__": true,
        "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230804/f09554dd2d5b39f04636dd31b782aab3.jpg",
        "alt": "发现-banner-朗逸领先版",
        "floatItems": [],
        "style": "1.2",
        "href": "pages/index/index?car=0C22",
        "type": "image",
        "class": "1",
        "oneclick": "",
        "hrefParamMz": ""
    },
    {
        "hrefParamSc": "SUV家族",
        "isshow__": true,
        "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230731/bc2082ddfd966834f316d1fed60b2af7.jpg",
        "alt": "发现-banner-SUV家族",
        "floatItems": [],
        "style": "1.1",
        "href": "https://m-mall.svw-volkswagen.com/marketing/activity/1684091248959012866?processKey=MF90189799&nodeKey=N1690353629211&utm_term=mp6-13-1",
        "type": "image",
        "class": "1",
        "oneclick": "",
        "hrefParamMz": ""
    },
    {
        "hrefParamSc": "ID.3 促销",
        "isshow__": true,
        "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230731/32aa299cb32aee7fb717064db23ed36e.jpg",
        "alt": "发现-banner-ID.3 促销",
        "floatItems": [],
        "style": "1.2",
        "href": "pages/index/index?car=E912",
        "type": "image",
        "class": "1",
        "oneclick": "",
        "uuid": "6c6b958f-4e39-4280-898a-85620f60436a",
        "hrefParamMz": ""
    },
    {
        "hrefParamSc": "途观家族",
        "isshow__": false,
        "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230731/ae4205f8474e42cabb23ed9877623e31.jpg",
        "alt": "发现-banner-途观L",
        "floatItems": [],
        "style": "1.2",
        "href": "pages/index/index?car=0T32",
        "type": "image",
        "class": "1",
        "oneclick": "",
        "hrefParamMz": ""
    },
    {
        "hrefParamSc": "新途岳",
        "isshow__": false,
        "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230731/ee61d767029b77f12444ee621d7e3dc6.jpg",
        "alt": "发现-banner-新途岳 王鹤棣",
        "floatItems": [],
        "style": "1.2",
        "href": "pages/index/index?car=B222",
        "type": "image",
        "class": "1",
        "oneclick": "",
        "uuid": "a835feef-45e1-4add-b399-a5970ddffa36",
        "hrefParamMz": ""
    },
    {
        "hrefParamSc": "Polo Plus",
        "isshow__": false,
        "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230619/d9fe32aa04a52ed47c7adf331fc7e3e9.jpg",
        "alt": "发现-banner-Polo Plus",
        "floatItems": [],
        "style": "1.2",
        "href": "pages/index/index?car=C313",
        "type": "image",
        "class": "1",
        "oneclick": "",
        "uuid": "fee67838-6f41-4940-b12a-a5c75441a565",
        "hrefParamMz": ""
    },
    {
        "hrefParamSc": "帕萨特",
        "isshow__": false,
        "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230428/af36b2fa53f0a7adaa963781e086eb2c.jpg",
        "alt": "发现-banner-帕萨特",
        "floatItems": [],
        "style": "1.2",
        "href": "pages/index/index?car=C432",
        "type": "image",
        "class": "1",
        "oneclick": "",
        "uuid": "ecd83cf3-e0d7-41f4-b672-88e2492a0874",
        "hrefParamMz": ""
    },
    {
        "hrefParamSc": "途安L",
        "isshow__": false,
        "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230801/8077e13f338ba116408c494da3eb3932.jpg",
        "alt": "发现-banner-途安L",
        "floatItems": [],
        "style": "1.2",
        "href": "pages/index/index?car=0R12",
        "type": "image",
        "class": "1",
        "oneclick": "",
        "hrefParamMz": ""
    },
    {
        "hrefParamSc": "保养",
        "isshow__": true,
        "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230628/9c956ce1220be44894799e30c3fafbb6.jpg",
        "alt": "发现-banner-保养",
        "floatItems": [],
        "style": "1.1",
        "href": "https://m-mall.svw-volkswagen.com/campaign/BYBZTY?utm_term=mp6-13-1",
        "type": "image",
        "class": "1",
        "oneclick": "",
        "hrefParamMz": ""
    }
],
      kvJsonNew:[],
      brandJson: {
        listBrand: [],
        list: [],
      },
      marveList:[
    {
        "floorId": "2b2d9fee-ae28-4ab1-a0ca-df6ced3845a0",
        "item": {
            "hrefParamSc": "发现-精彩活动-朗逸领先版",
            "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230804/f90556ec703a9e84f0f33b03a9f1f808.jpg",
            "alt": "朗逸星空领先版上市，8月限时综合优惠3万元",
            "floatItems": [
                {
                    "isshow__": true,
                    "style": "",
                    "href": "",
                    "type": "button",
                    "value": "即刻预约",
                    "oneclick": "",
                    "class": "",
                    "hrefParamMz": ""
                }
            ],
            "style": "1.2",
            "href": "pages/index/index?car=0C22",
            "type": "image",
            "class": "1",
            "oneclick": "",
            "uuid": "a36c20f4-0be3-460f-96d4-31c31e9734a7",
            "hrefParamMz": "综合优惠后11.39万"
        },
        "templateName": "activity",
        "templateClass": "",
        "templateCode": "cms-base-image",
        "templateStyle": "",
        "templateId": "1649277734697242625",
        "templateLayout": "",
        "uuid": "2b2d9fee-ae28-4ab1-a0ca-df6ced3845a0",
        "isShow": true
    },
    {
        "floorId": "3ce6b136-1b5b-49c5-ac4c-87bdb5e1c626",
        "item": {
            "hrefParamSc": "发现-精彩活动-SUV家族",
            "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230731/2289acacb95b50387ad291cc22c38036.jpg",
            "alt": "购上汽大众SUV赢豪礼享优惠",
            "floatItems": [
                {
                    "isshow__": true,
                    "style": "",
                    "href": "",
                    "type": "button",
                    "value": "即刻预约",
                    "oneclick": "",
                    "class": "",
                    "hrefParamMz": ""
                }
            ],
            "style": "1.1",
            "href": "https://m-mall.svw-volkswagen.com/marketing/activity/1684091248959012866?processKey=MF90189799&nodeKey=N1690353629211&utm_term=mp6-6-8",
            "type": "image",
            "class": "1",
            "oneclick": "",
            "uuid": "53439119-aea3-411f-93b6-6c9db2786e97",
            "hrefParamMz": "单车至高60,000元综合优惠"
        },
        "templateName": "activity",
        "templateClass": "",
        "templateCode": "cms-base-image",
        "templateStyle": "",
        "templateId": "1649277734697242625",
        "templateLayout": "",
        "uuid": "3ce6b136-1b5b-49c5-ac4c-87bdb5e1c626",
        "isShow": true
    },
    {
        "floorId": "c6840ac9-7b2d-4804-a780-e0b315af521d",
        "item": {
            "hrefParamSc": "发现-精彩活动-ID.3 促销",
            "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230731/cd1d753ae4c20cb6da6044f990497ab0.jpg",
            "alt": "品质乐趣纯电跨界车 ID.3 限时惊爆价12.59万元起",
            "floatItems": [
                {
                    "hrefParamSc": "",
                    "isshow__": true,
                    "style": "",
                    "href": "",
                    "type": "button",
                    "value": "了解更多",
                    "oneclick": "",
                    "class": "",
                    "hrefParamMz": ""
                }
            ],
            "style": "1.2",
            "href": "pages/index/index?car=E912",
            "type": "image",
            "class": "1",
            "oneclick": "",
            "uuid": "0791424b-2ca8-442f-8dd1-65cfb0439818",
            "hrefParamMz": "品质乐趣纯电跨界车，立减3.7万元，限时惊爆价12.59万元起！"
        },
        "templateName": "activity",
        "templateClass": "",
        "templateCode": "cms-base-image",
        "templateStyle": "",
        "templateId": "1649277734697242625",
        "templateLayout": "",
        "uuid": "c6840ac9-7b2d-4804-a780-e0b315af521d",
        "isShow": true
    },
    {
        "floorId": "cd685fb4-b6b4-4700-bd16-09e159ae8a80",
        "item": {
            "hrefParamSc": "发现-精彩活动-保养",
            "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230628/9988cca472fedb1965c1bea3cbe50014.jpg",
            "alt": "上汽大众售后保养套餐火热上线！",
            "floatItems": [
                {
                    "isshow__": true,
                    "style": "",
                    "href": "",
                    "type": "button",
                    "value": "立即购买",
                    "oneclick": "",
                    "class": "",
                    "hrefParamMz": ""
                }
            ],
            "style": "1.2",
            "href": "pages/index/index",
            "type": "image",
            "class": "1",
            "oneclick": "",
            "uuid": "0ff823fd-5a83-4afd-b10a-d13f098e5378",
            "hrefParamMz": "养车就选TA！省钱省时更省心的保养套餐来了"
        },
        "templateName": "activity",
        "templateClass": "",
        "templateCode": "cms-base-image",
        "templateStyle": "",
        "templateId": "1649277734697242625",
        "templateLayout": "",
        "uuid": "cd685fb4-b6b4-4700-bd16-09e159ae8a80",
        "isShow": true
    },
    {
        "floorId": "680aae86-4b69-48b7-b3e8-cfd786350553",
        "item": {
            "hrefParamSc": "发现-精彩活动-途观L",
            "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230804/ae720cba7f254345b1b8a7000f16d976.jpg",
            "alt": "盛夏狂欢限时直降，途观L 16.99万元起！",
            "floatItems": [
                {
                    "isshow__": true,
                    "style": "",
                    "href": "",
                    "type": "button",
                    "value": "即刻预约",
                    "oneclick": "",
                    "class": "",
                    "hrefParamMz": ""
                }
            ],
            "style": "1.2",
            "href": "pages/index/index?car=0T32",
            "type": "image",
            "class": "1",
            "oneclick": "",
            "uuid": "0590ea22-8ba0-4171-a051-294aa70a1b92",
            "hrefParamMz": "#IQ颜值双在线，即刻下订享多重惊喜礼遇"
        },
        "templateName": "activity",
        "templateClass": "",
        "templateCode": "cms-base-image",
        "templateStyle": "",
        "templateId": "1649277734697242625",
        "templateLayout": "",
        "uuid": "680aae86-4b69-48b7-b3e8-cfd786350553",
        "isShow": true
    },
    {
        "floorId": "ead930e0-98ff-4540-8fe8-879a842fe932",
        "item": {
            "hrefParamSc": "发现-精彩活动-新途岳 王鹤棣",
            "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230731/3178377960e5bb8338c4d9da0260a2f5.jpg",
            "alt": "15.86万元起，新途岳携手王鹤棣，悦心上市！",
            "floatItems": [
                {
                    "hrefParamSc": "",
                    "isshow__": true,
                    "style": "",
                    "href": "",
                    "type": "button",
                    "value": "即刻下订",
                    "oneclick": "",
                    "class": "",
                    "hrefParamMz": ""
                }
            ],
            "style": "1.2",
            "href": "pages/index/index?car=B222",
            "type": "image",
            "class": "1",
            "oneclick": "",
            "uuid": "9acf3baa-745c-4175-a57d-eb59735e5715",
            "hrefParamMz": "悦行出众，高颜值品质SUV顶流——新途岳New Tharu"
        },
        "templateName": "activity",
        "templateClass": "",
        "templateCode": "cms-base-image",
        "templateStyle": "",
        "templateId": "1649277734697242625",
        "templateLayout": "",
        "uuid": "ead930e0-98ff-4540-8fe8-879a842fe932",
        "isShow": true
    },
    {
        "floorId": "8b907df5-73af-489c-ba93-9d20698ce8b7",
        "item": {
            "hrefParamSc": "发现-精彩活动-Polo Plus",
            "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230731/1a260820674e061c976693e7597f764c.jpg",
            "alt": "9.09万元起，Polo Plus 2023款焕新上市！",
            "floatItems": [
                {
                    "hrefParamSc": "",
                    "isshow__": true,
                    "style": "",
                    "href": "",
                    "type": "button",
                    "value": "即刻预约",
                    "oneclick": "",
                    "class": "", 
                    "hrefParamMz": ""
                }
            ],
            "style": "1.2",
            "href": "pages/index/index?car=C313",
            "type": "image",
            "class": "1",
            "oneclick": "",
            "uuid": "e20f2089-d7fd-4a51-8b03-71af8e54cbee",
            "hrefParamMz": "送你一朵小红花，一起绽放我所爱"
        },
        "templateName": "activity",
        "templateClass": "",
        "templateCode": "cms-base-image",
        "templateStyle": "",
        "templateId": "1649277734697242625",
        "templateLayout": "",
        "uuid": "8b907df5-73af-489c-ba93-9d20698ce8b7",
        "isShow": true
    },
    {
        "floorId": "057270fa-a9bf-487e-b6cf-c38d5794b4a1",
        "item": {
            "hrefParamSc": "发现-精彩活动-帕萨特",
            "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230731/c9123fbda9af60eb457c3dc6bb9c06c6.jpg",
            "alt": "订购帕萨特2023款，立享至高综合优惠30,000元",
            "floatItems": [
                {
                    "hrefParamSc": "",
                    "isshow__": true,
                    "style": "",
                    "href": "",
                    "type": "button",
                    "value": "即刻预约",
                    "oneclick": "",
                    "class": "",
                    "hrefParamMz": ""
                }
            ],
            "style": "1.2",
            "href": "pages/index/index?car=C432",
            "type": "image",
            "class": "1",
            "oneclick": "",
            "uuid": "05444270-f23d-4e21-82cd-2d7fc56e8624",
            "hrefParamMz": "18.19万元起，我的选择 成就我的世界"
        },
        "templateName": "activity",
        "templateClass": "",
        "templateCode": "cms-base-image",
        "templateStyle": "",
        "templateId": "1649277734697242625",
        "templateLayout": "",
        "uuid": "057270fa-a9bf-487e-b6cf-c38d5794b4a1",
        "isShow": true
    },
    {
        "floorId": "7ae9a3e3-04f4-43b1-a6e7-ec426cf4f2fd",
        "item": {
            "hrefParamSc": "发现-精彩活动-途安L",
            "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230801/61d0b2893100c65bdd9ff5426ed0e731.jpg",
            "alt": "订购途安L，立享至高2年0利率",
            "floatItems": [
                {
                    "isshow__": true,
                    "style": "",
                    "href": "",
                    "type": "button",
                    "value": "即刻预约",
                    "oneclick": "",
                    "class": "",
                    "hrefParamMz": ""
                }
            ],
            "style": "1.2",
            "href": "pages/index/index?car=0R12",
            "type": "image",
            "class": "1",
            "oneclick": "",
            "uuid": "3f6d52ef-536c-44bd-b6d9-845f8c8cc7f4",
            "hrefParamMz": "16.68万元起，实力承载美好"
        },
        "templateName": "activity",
        "templateClass": "",
        "templateCode": "cms-base-image",
        "templateStyle": "",
        "templateId": "1649277734697242625",
        "templateLayout": "",
        "uuid": "7ae9a3e3-04f4-43b1-a6e7-ec426cf4f2fd",
        "isShow": true
    }
], //精彩活动
      allCar: [],
      systemInfo: null,
      kvHeight: parseInt((1341 / 1227) * uni.getSystemInfoSync().screenWidth),
      scrollTop: 0,
      tabsWhite: false,
      navTop: 0,
	    opacity:0,
      tabsOpacity: 0,
      buttonList: [
    {
      "hrefParamSc": "",
      "isshow__": true,
      "style": "1.2",
      "href": "pages/testDrive/testDrive",
      "type": "button",
      "value": "订购咨询",
      "oneclick": "",
      "class": "",
      "hrefParamMz": ""
    },
    {
      "hrefParamSc": "",
      "isshow__": true,
      "style": "1.2",
      "href": "pages/dealer/dealer",
      "type": "button",
      "value": "查找经销商",
      "oneclick": "",
      "class": "3",
      "hrefParamMz": ""
    }
  ],
      dealerTitle: '预约品鉴',
    }
  },
  watch: {
    scrollTop() {
      // 置顶按钮根据滑动距离改变透明度
      if (this.systemInfo && this.kvHeight)
        this.tabsOpacity = (this.scrollTop / this.kvHeight).toFixed(5)
    },
  },
  async onReady() {
    // const {ddd}=await getTest()
    // console.log(ddd)
    await this.$onLaunched
      // this.kvJson = this.countData('cms-base-slideshow',"banner") //轮播
      // console.log(this.kvJson)
      // 公共车型
      // const allCarData = this.countDataList('cms-base-imagelist','brandmodels')
      // console.log(allCarData)
      // this.allCar = allCarData
      const allCarData=[
    {
        "floorId": "2d0f32bc-a67b-4fa0-8179-3a52a3206bf4",
        "item": {
            "subTitle": {},
            "background": {},
            "more": {},
            "title": {},
            "items": [
                {
                    "hrefParamSc": "162,888元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230414/2ec1fb7ce08bc23ba8dde27c34367123.png",
                    "alt": "ID.3",
                    "floatItems": [
                        {
                            "isshow__": false,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "品质乐趣纯电跨界车<br>ID.预约试驾</n>品质乐趣纯电跨界车",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        },
                        {
                            "isshow__": false,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "默认选中车型",
                            "class": "",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "E912",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价162,888元起",
                    "oneclick": "",
                    "hrefParamMz": "17"
                },
                {
                    "hrefParamSc": "195,888元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230414/3b87251cd39847ab9f2697d2f8e4edc0.png",
                    "alt": "ID.4 X",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "品质纯电SUV<br>ID.预约试驾</n>品质纯电SUV",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "E413",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价195,888元起",
                    "oneclick": "",
                    "hrefParamMz": "16"
                },
                {
                    "hrefParamSc": "259,888元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230414/198f606906a16d55eb6163976d3728a9.png",
                    "alt": "ID.6 X ",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "品质七座纯电SUV<br>ID.预约试驾</n>品质七座纯电SUV",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "E513",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价259,888元起",
                    "oneclick": "",
                    "hrefParamMz": "15"
                }
            ],
            "uuid": "4b2bb503-3d22-47a7-bcb2-a5fa17a5b5aa"
        },
        "templateName": "brandmodels",
        "templateClass": "ID.纯电",
        "priceType": "V",
        "templateCode": "cms-base-imagelist",
        "templateStyle": "nga",
        "templateId": "1649275743665328130",
        "templateLayout": "",
        "uuid": "2d0f32bc-a67b-4fa0-8179-3a52a3206bf4",
        "isShow": true
    },
    {
        "floorId": "67ed380e-99bc-42e8-bd56-a88bbe670c3a",
        "item": {
            "subTitle": {},
            "background": {},
            "more": {},
            "title": {},
            "items": [
                {
                    "hrefParamSc": "93,990元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230607/e45a932304e813f966943f051fec7edb.png",
                    "alt": "朗逸新锐",
                    "floatItems": [
                        {
                            "isshow__": false,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "500万国民家轿新选择<br>预约品鉴</n>500万国民家轿新选择",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "DC12",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价93,990元起",
                    "oneclick": "",
                    "hrefParamMz": "7"
                },
                {
                    "hrefParamSc": "343,000元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/d15c98f87282d8442b2bfd637a7766f1.png",
                    "alt": "辉昂",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "德系行政级旗舰座驾<br>预约品鉴</n>德系行政级旗舰座驾",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "3E84",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价343,000元起",
                    "oneclick": "",
                    "hrefParamMz": "8"
                },
                {
                    "hrefParamSc": "181,900元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230510/1b717fc340e453c2d387fe3e8597dfb8.png",
                    "alt": "帕萨特",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "B级车品质之选<br>预约品鉴</n>B级车品质之选",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "C432",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价181,900元起",
                    "oneclick": "",
                    "hrefParamMz": "9"
                },
                {
                    "hrefParamSc": "150,900元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/dbc8451832f54453fd76ce9110774fa1.png",
                    "alt": "凌渡L",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "辣感无框轿跑<br>预约品鉴</n>辣感无框轿跑",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "DM12",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价150,900元起",
                    "oneclick": "",
                    "hrefParamMz": "10"
                },
                {
                    "hrefParamSc": "120,900元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/e3dd9ccb86205b052aa12d53e4442c51.png",
                    "alt": "朗逸",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "五百万国民之选<br>预约品鉴</n>五百万国民之选",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "0C22",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价120,900元起",
                    "oneclick": "",
                    "hrefParamMz": "11"
                },
                {
                    "hrefParamSc": "100,900元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/2425a6ef791e86b50a7a2cd71ad03bfe.png",
                    "alt": "朗逸启航",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "家用品质座驾<br>预约品鉴</n>家用品质座驾",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "186C",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价100,900元起",
                    "oneclick": "",
                    "hrefParamMz": "12"
                },
                {
                    "hrefParamSc": "87,900元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/c2e8e7ea621ec7756239bec5f8eb3764.png",
                    "alt": "桑塔纳",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "品质轿车<br>预约品鉴</n>品质轿车",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "BR45",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价87,900元起",
                    "oneclick": "",
                    "hrefParamMz": "13"
                },
                {
                    "hrefParamSc": "90,900元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20221027/1187b2716f5c2f77c1fc56822fb51a1d.png",
                    "alt": "Polo Plus",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "悦享出色城市两厢车<br>预约品鉴</n>悦享出色城市两厢车",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "C313",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价90,900元起",
                    "oneclick": "",
                    "hrefParamMz": "14"
                }
            ],
            "uuid": "74f0f669-c348-41e0-be75-182a969db478"
        },
        "templateName": "brandmodels",
        "templateClass": "轿车",
        "templateCode": "cms-base-imagelist",
        "templateStyle": "feinga",
        "templateId": "1649275743665328130",
        "templateLayout": "",
        "uuid": "67ed380e-99bc-42e8-bd56-a88bbe670c3a",
        "isShow": true
    },
    {
        "floorId": "7d2eb604-cbef-45c7-9a54-b1e4fcd380f1",
        "item": {
            "subTitle": {},
            "background": {},
            "more": {},
            "title": {},
            "items": [
                {
                    "hrefParamSc": "295,000元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/88ed37b59ba286690488c9b5b26be27e.png",
                    "alt": "途昂",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "豪华旗舰SUV<br>预约品鉴</n>豪华旗舰SUV",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "CU14",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价295,000元起",
                    "oneclick": "",
                    "hrefParamMz": "1"
                },
                {
                    "hrefParamSc": "285,000元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220926/fe01ba1105be489110a566bb75c9cc7a.png",
                    "alt": "途昂X",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "豪华旗舰SUV<br>预约品鉴</n>豪华旗舰SUV",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "CVC4",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价285,000元起",
                    "oneclick": "",
                    "hrefParamMz": "2"
                },
                {
                    "hrefParamSc": "199,800元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230518/7cbeed681eb439e699392ff46e3f199c.png",
                    "alt": "途观L",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "领潮智能中型SUV<br>预约品鉴</n>领潮智能中型SUV",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "0T32",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价199,800元起",
                    "oneclick": "",
                    "hrefParamMz": "3"
                },
                {
                    "hrefParamSc": "240,800元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220825/d9c19ec91aeb5b9c825895910410d3b4.png",
                    "alt": "途观X",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "高端型格轿跑SUV<br>预约品鉴</n>高端型格轿跑SUV",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "0T47",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价240,800元起",
                    "oneclick": "",
                    "hrefParamMz": "4"
                },
                {
                    "hrefParamSc": "158,600元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20230327/aa565060ae12356e4cc4830b4681c977.png",
                    "alt": "途岳",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "高颜值品质SUV顶流<br>预约品鉴</n>高颜值品质SUV顶流",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "B222",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价158,600元起",
                    "oneclick": "",
                    "hrefParamMz": "5"
                },
                {
                    "hrefParamSc": "115,900元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/0a0d8e638298bea91727ee1ffbcc7a47.png",
                    "alt": "途铠",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "实力派城市SUV<br>预约品鉴</n>实力派城市SUV",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "C812",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价115,900元起",
                    "oneclick": "",
                    "hrefParamMz": "6"
                }
            ],
            "uuid": "bd1ffd47-4ec8-4562-8783-2883699e7c71"
        },
        "templateName": "brandmodels",
        "templateClass": "SUV",
        "templateCode": "cms-base-imagelist",
        "templateStyle": "feinga",
        "templateId": "1649275743665328130",
        "templateLayout": "",
        "uuid": "7d2eb604-cbef-45c7-9a54-b1e4fcd380f1",
        "isShow": true
    },
    {
        "floorId": "4a3ad927-69b9-4429-8d59-7745abe46bb0",
        "item": {
            "subTitle": {},
            "background": {},
            "more": {},
            "title": {},
            "items": [
                {
                    "hrefParamSc": "289,800元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/40c540aa92a7800281968ff656c12f13.png",
                    "alt": "威然",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "豪华7座MPV<br>预约品鉴</n>豪华7座MPV",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "CF12",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价289,800元起",
                    "oneclick": "",
                    "hrefParamMz": "18"
                },
                {
                    "hrefParamSc": "166,800元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/b3ed9e0e5d36e73cbaa0a69d923e192c.png",
                    "alt": "途安L",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "德系全能MPV<br>预约品鉴</n>德系全能MPV",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "0R12",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价166,800元起",
                    "oneclick": "",
                    "hrefParamMz": "19"
                }
            ],
            "uuid": "6ccde261-0459-41ef-8124-23906d30e37a"
        },
        "templateName": "brandmodels",
        "templateClass": "MPV",
        "templateCode": "cms-base-imagelist",
        "templateStyle": "feinga",
        "templateId": "1649275743665328130",
        "templateLayout": "",
        "uuid": "4a3ad927-69b9-4429-8d59-7745abe46bb0",
        "isShow": true
    },
    {
        "floorId": "457e4cb3-ebc9-4fd9-a4e0-2fe19d64b4a5",
        "item": {
            "subTitle": {},
            "background": {},
            "more": {},
            "title": {},
            "items": [
                {
                    "hrefParamSc": "261,050元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/c299c694c536011c282cfaf240aeb806.png",
                    "alt": "途观L 插电混动",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "<br>预约品鉴",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "0T3P",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价261,050元起",
                    "oneclick": "",
                    "hrefParamMz": "20"
                },
                {
                    "hrefParamSc": "233,150元起",
                    "isshow__": true,
                    "src": "https://brand2.svw-volkswagen.com/cms/prod/I/20220815/128d4e6201eab5ab186160ab88c0200b.png",
                    "alt": "帕萨特 插电混动",
                    "floatItems": [
                        {
                            "isshow__": true,
                            "style": "",
                            "href": "",
                            "type": "text",
                            "value": "<br>预约品鉴",
                            "class": "retention",
                            "oneclick": "",
                            "hrefParamMz": ""
                        }
                    ],
                    "style": "C43P",
                    "href": "",
                    "type": "image",
                    "class": "建议零售价233,150元起",
                    "oneclick": "",
                    "hrefParamMz": "21"
                }
            ],
            "uuid": "ade8661f-96c9-4154-80aa-a5545339093c"
        },
        "templateName": "brandmodels",
        "templateClass": "新能源",
        "templateCode": "cms-base-imagelist",
        "templateStyle": "feinga",
        "templateId": "1649275743665328130",
        "templateLayout": "",
        "uuid": "457e4cb3-ebc9-4fd9-a4e0-2fe19d64b4a5",
        "isShow": true
    }
]
      this.brandJson = {
        listBrand: allCarData,
        list:allCarData[1].item.items,
      }
      //精彩活动
      // this.marveList = this.countDataList('cms-base-image',"activity")
      // console.log(this.marveList)
      //按钮列表
      // this.buttonList = this.countDataArr('topbar').items
      this.dealerTitle=this.buttonList[0].value
    
  },
  mounted() {
    // 获取屏幕信息
   

    // 页面浏览-自定义事件（发现）
    // this.$Global.trackViewScreen('发现')
  },
  methods: {
    
    // 页面跳转
    toPage(item) {
      const data = item.item
      const type = data.style
      if (data.href) {
        // 外链
        if (type === '1.1') {
          const url = encodeURIComponent(data.href)
          uni.navigateTo({
            url: `/pages/index/index?url=${url}`,
          })
        }
        // 小程序内跳转
        else {
          uni.navigateTo({
            url: `/${data.href}`,
          })
        }
      }
    },
    toHref(url) {
      uni.navigateTo({
        url:`/${url}`,
      })
    },
  },
}
</script>

<style lang="scss" scoped>
.find-content {
  .activity {
    padding-top: 40rpx;
    margin-bottom: 48rpx;
    .title {
      margin-bottom: 50rpx;
      font-family: 'HYQiHei-80S', 'VWText-Bold';
      color: #333333;
      line-height: 52rpx;
      font-size: 36rpx;
    }
  }
  .btn {
    height: 80rpx;
    margin: 48rpx 24rpx;
    border-radius: 40rpx;
    border: 2rpx solid #00b0f0;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #00b0f0;
    font-size: 32rpx;
    position: relative;
  }
  
  .imgB{ position: absolute; width: 50%; height: 100%; left: 0; top: 0; }
  .list-box {
    margin-top: 48rpx;
    border-bottom: 1px solid rgba(223, 228, 232, 0.25);
    &:first-child {
      margin-top: 0;
    }
    .img {
      width: 100%;
      display: block;
      border-radius: 4rpx;
    }
    .alt {
      margin-top: 32rpx;
      font-size: 32rpx;
      line-height: 1;
      text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
    }
    .desc {
      margin-top: 32rpx;
      font-size: 24rpx;
      color: #96a3a8;
    }
  }
  .view-border {
    margin: 0rpx 32rpx 40rpx 32rpx;
  }
  
  .live{ position: fixed; right:32rpx; top:70%;}
}
.top-button {
  position: fixed;
  left: 0;
  top: 0;
  right: 0;
  background: #fff;
  height: 110rpx;
  display: flex;
  align-items: center;
  justify-content: space-between;
  z-index: 10;
  opacity: 0;
  box-sizing: content-box;
  .logo {
    height: 40rpx;
    max-width: 134rpx;
  }
  .btn-list {
    display: flex;
    .btnb {
      // width: 190rpx;
      // height: 60rpx;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 24rpx;
      // line-height: 24rpx;
      border: 2rpx solid #00b0f0;
      padding:18rpx 30rpx;
      border-radius: 60rpx;
      max-height: 64rpx;
      min-width: 180rpx;
      color: #00b0f0;
      &:first-child {
        margin-right: 32rpx;
      }
    }
    .pinjian {
      background: #00b0f0;
      color: #ffffff;
    }
  }
}
</style>
