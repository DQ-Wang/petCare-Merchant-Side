<template>
  <view class="section-card">
    <view class="section-title">订单详情</view>
    <view class="divider"></view>

    <view class="user-row">
      <image class="avatar" :src="orderInfo.avatar" mode="aspectFill" />
      <view class="user-meta">
        <text class="user-name">{{ orderInfo.userName }}</text>
        <text class="meta-text">联系电话：{{ orderInfo.phone }}</text>
        <text class="meta-text">洗护时间：{{ orderInfo.serviceTime }}</text>
      </view>
    </view>

    <view class="service-list">
      <view class="info-line">
        <text class="label">洗护对象：</text>
        <text class="value">{{ orderInfo.petType }}</text>
      </view>
      <view class="info-line">
        <text class="label">洗护套餐：</text>
        <text class="value">{{ orderInfo.packageName }}</text>
      </view>
      <view class="info-line">
        <text class="label">基础服务：</text>
        <text class="value">{{ orderInfo.baseService }}</text>
      </view>
      <view class="info-line">
        <text class="label">增值服务：</text>
        <text class="value">{{ orderInfo.extraService }}</text>
      </view>
    </view>

    <view class="divider total-divider"></view>
    <view class="total-row">
      <text class="total-text">总计 <text class="total-price">¥{{ orderInfo.totalPrice }}</text></text>
    </view>
  </view>
</template>

<script setup>
defineProps({
  orderInfo: {
    type: Object,
    default: () => ({})
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

.user-row {
  display: flex;
  align-items: center;
  gap: 22rpx;
}

.avatar {
  width: 120rpx;
  height: 120rpx;
  border-radius: 50%;
  background: #f4f5f9;
  flex-shrink: 0;
}

.user-meta {
  display: flex;
  flex-direction: column;
  gap: 10rpx;
}

.user-name {
  font-size: 30rpx;
  font-weight: 700;
  color: #333333;
}

.meta-text {
  font-size: 26rpx;
  color: #666666;
}

.service-list {
  margin-top: 28rpx;
  display: flex;
  flex-direction: column;
  gap: 16rpx;
}

.info-line {
  display: flex;
  align-items: flex-start;
}

.label {
  color: #335700;
  font-size: 27rpx;
  font-weight: 700;
}

.value {
  flex: 1;
  font-size: 27rpx;
  color: #333333;
  line-height: 1.6;
}

.total-divider {
  margin-bottom: 20rpx;
}

.total-row {
  display: flex;
  justify-content: flex-end;
}

.total-text {
  font-size: 30rpx;
  color: #333333;
  font-weight: 600;
}

.total-price {
  color: #d63a3a;
  font-weight: 700;
}
</style>
