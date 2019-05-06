<script>
export default {
  created () {
    // 调用API从本地缓存中获取数据
    /*
     * 平台 api 差异的处理方式:  api 方法统一挂载到 mpvue 名称空间, 平台判断通过 mpvuePlatform 特征字符串
     * 微信：mpvue === wx, mpvuePlatform === 'wx'
     * 头条：mpvue === tt, mpvuePlatform === 'tt'
     * 百度：mpvue === swan, mpvuePlatform === 'swan'
     * 支付宝(蚂蚁)：mpvue === my, mpvuePlatform === 'my'
     */
    this.test(wx)
  },
  methods: {
    test(wx) {
      wx.showLoading({
        title: '加载中'
      })
      setTimeout(function () {
        wx.hideLoading()
      }, 2000)
      // wx.showModal({
      //   title: '温馨提示',
      //   content: '当前微信版本过低，无法更新小程序，请升级微信到最新版本！'
      // })
    }
  }
}
</script>

<style lang="scss">

</style>
