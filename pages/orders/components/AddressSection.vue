<template>
  <view class="section-card" @click="$emit('navigate')">
    <view class="section-title">上门地址</view>
    <view class="divider"></view>
    <view class="address-row">
      <text class="address-text">{{ address }}</text>
      <text class="arrow">></text>
    </view>
  </view>
</template>

<script setup>
defineProps({
  address: {
    type: String,
    default: ''
  }
})

defineEmits(['navigate'])
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

.address-row {
  display: flex;
  align-items: center;
  gap: 16rpx;
}

.address-text {
  flex: 1;
  font-size: 28rpx;
  line-height: 1.6;
  color: #333333;
}

.arrow {
  color: #b2d76e;
  font-size: 32rpx;
  font-weight: 700;
}
</style>
