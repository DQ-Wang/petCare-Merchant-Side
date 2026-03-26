<template>
  <view class="section-card">
    <view class="section-title">订单备注</view>
    <view class="divider"></view>
    <text class="remark-text">{{ remark }}</text>
  </view>
</template>

<script setup>
defineProps({
  remark: {
    type: String,
    default: ''
  }
})
</script>

<style scoped>
.section-card {
  background: #ffffff;
  border-radius: 16rpx;
  padding: 28rpx 30rpx;
}

.section-title {
  font-size: 32rpx;
  font-weight: 700;
  color: #333333;
}

.divider {
  height: 1rpx;
  background: #ececec;
  margin: 22rpx 0;
}

.remark-text {
  font-size: 28rpx;
  line-height: 1.8;
  color: #333333;
}
</style>
