<template>
  <div>
    <swiper 
      v-if="imgUrls.length > 0" 
      class="swiper-container" 
      :circular="true"
      :indicator-dots="true"
      indicator-active-color="#42b983"
      :autoplay="true"
    >
      <block v-for="(item, index) in imgUrls" :key="index">
        <swiper-item>
          <image class="swiper-img" :src="item" mode="scaleToFill"></image>
        </swiper-item>
      </block>
    </swiper>
  </div>
</template>

<script>
import card from '@/components/card'

export default {
  components: {
    card
  },
  data() {
    return {
      imgUrls: [
        'http://mss.sankuai.com/v1/mss_51a7233366a4427fa6132a6ce72dbe54/newsPicture/05558951-de60-49fb-b674-dd906c8897a6',
        'http://mss.sankuai.com/v1/mss_51a7233366a4427fa6132a6ce72dbe54/coursePicture/0fbcfdf7-0040-4692-8f84-78bb21f3395d',
        'http://mss.sankuai.com/v1/mss_51a7233366a4427fa6132a6ce72dbe54/management-school-picture/7683b32e-4e44-4b2f-9c03-c21f34320870'
      ]
    }
  },
  created() {}
}
</script>

<style lang="scss" scoped>
.swiper-container {
  width: 90%;
  margin: 0 auto;
  .swiper-img {
    width: 100%;
  }
}
</style>
