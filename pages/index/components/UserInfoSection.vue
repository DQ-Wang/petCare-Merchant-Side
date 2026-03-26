<template>
  <view class="user-card">
    <view class="avatar-wrap"></view>
    <view class="user-meta">
      <text class="user-name">{{ userInfo.nickname }}</text>
      <text class="platform">{{ userInfo.platform }}</text>
    </view>
    <image class="decorator" src="/static/workbench/user/decorator-dog.png" mode="aspectFit" />
  </view>
</template>

<script setup>
defineProps({
  userInfo: {
    type: Object,
    default: () => ({})
  }
})
</script>

<style scoped>
.user-card {
  padding: 10rpx 12rpx 26rpx;
  display: flex;
  align-items: center;
  position: relative;
}

.avatar-wrap {
  width: 120rpx;
  height: 120rpx;
  border-radius: 50%;
  background: #d5e6ba;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  margin-right: 30rpx;
}

.user-meta {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 10rpx;
}

.user-name {
  font-size: 34rpx;
  font-weight: 700;
  color: #333333;
}

.platform {
  font-size: 24rpx;
  color: #6f6f6f;
}

.decorator {
  width: 200rpx;
  height: 200rpx;
  flex-shrink: 0;
}
</style>
