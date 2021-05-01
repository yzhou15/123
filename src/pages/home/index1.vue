<template>
  <view>首页
    <text class="iconfont iconvideocamera"></text>
    <uni-badge text="1"></uni-badge><uni-badge text="2" type="success" ></uni-badge>
    <uni-badge text="3" type="primary" :inverted="true"></uni-badge>

  </view>
</template>

<script>
import {uniBadge} from '@dcloudio/uni-ui'
export default {
  name: "index",
  components:{
    uniBadge
  },
  onload(){
    // http://157.122.54.189:9088/image/v3/homepage/vertical?limit=10&order=hot&skip=2
    // 1.原生的微信小程序的api
    wx.request({
      url:"http://157.122.54.189:9088/image/v3/homepage/vertical?limit=10&order=hot&skip=2",
      success(res){
        console.log(res);
      }
    })

    // 2. uni-api
    uni.request({
      uni:"http://157.122.54.189:9088/image/v3/homepage/vertical?limit=10&order=hot&skip=2"
    }).then(res => {
      console.log(res);
    })
  }
}
</script>

<style scoped>

</style>