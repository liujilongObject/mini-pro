<template>
  <div class="home-container">
    <p class="date">{{ date }}</p>
    <p class="test">
      <span class="counter">KKKKK</span>
      <icon class="icon" type="success" />
    </p>
    <p class="scroll">
      <scroll-view
        scroll-y
        style="height: 200rpx;"
        :scroll-top="scrollTop"
        class="scroll-wrapper"
        scroll-with-animation
      >
        <div>aaaaa</div>
        <div>bbbbb</div>
        <div>ccccc</div>
        <div>ddddd</div>
        <div>eeeee</div>
        <div>aaaaa</div>
        <div>bbbbb</div>
        <div>ccccc</div>
        <div>ddddd</div>
        <div>eeeee</div>
      </scroll-view>
    </p>
    <i class="icon mt-add-o"></i>
  </div>
</template>

<script>
import { formatTime } from '@/utils'

export default {
  data () {
    return {
      date: '',
      scrollTop: 0
    }
  },
  components: {},
  methods: {
    getDate() {
      let date = formatTime(new Date())
      this.date = date
    },
    setTimer() {
      setInterval(() => {
        this.getDate()
      }, 1000)
    },
    startScroll() {
      setInterval(() => {
        this.scrollTop += 30
        if (this.scrollTop === 240) {
          this.scrollTop = 0
        }
      }, 1000)
    }
  },
  created () {
    this.setTimer()
    // this.startScroll()
  }
}
</script>

<style lang="scss" scoped>
.home-container {
  text-align: center;
  .date {
    padding: 20rpx;
  }
  .test {
    // overflow: hidden;
    width: 50%;
    margin: 0 auto;
    @include clearfix;
    .counter {
      color: orange;
      font-size: 50rpx;
      float: left;
    }
    .icon {
      float: left;
      margin: 10rpx 0 0 10rpx;
    }
  }
  .scroll {
    .scroll-wrapper {
      div {
        height: 60rpx;
      }
    }
  }
}
</style>
