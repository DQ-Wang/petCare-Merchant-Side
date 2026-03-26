<template>
  <view class="page">
    <!-- 标签导航区 -->
    <view class="tabs">
      <view 
        v-for="tab in tabs" 
        :key="tab"
        :class="['tab-item', { active: currentTab === tab }]"
        @click="currentTab = tab">
        {{ tab }}
      </view>
    </view>
    
    <!-- 订单列表区 -->
    <view class="order-list">
      <!-- 上门订单1 -->
      <view class="order-card">
        <view class="card-header">
          <text class="order-type">上门订单</text>
          <text class="time">7月13日（本周日）13:00</text>
          <text class="price">¥45</text>
        </view>
        <view class="address-main">厦门大学翔安校区国光宿舍国光15</view>
        <view class="address-detail">福建省厦门市翔安区xx路xx号</view>
        <view class="service">小型犬基础养护、基础检查</view>
        <view class="buttons">
          <view class="btn-reject">拒绝</view>
          <view class="btn-accept">接受</view>
        </view>
      </view>
      
      <!-- 上门订单2 -->
      <view class="order-card">
        <view class="card-header">
          <text class="order-type">上门订单</text>
          <text class="time">7月13日（本周日）13:00</text>
          <text class="price">¥45</text>
        </view>
        <view class="address-main">厦门大学翔安校区国光宿舍国光15</view>
        <view class="address-detail">福建省厦门市翔安区xx路xx号</view>
        <view class="service">小型犬基础养护、基础检查</view>
        <view class="buttons">
          <view class="btn-reject">拒绝</view>
          <view class="btn-accept">接受</view>
        </view>
      </view>
      
      <!-- 到店订单 -->
      <view class="order-card">
        <view class="card-header">
          <text class="order-type">到店订单</text>
          <text class="time">7月13日（本周日）13:00</text>
          <text class="price">¥45</text>
        </view>
        <view class="address-main">汪汪喵宠物洗护服务中心宝龙一城店</view>
        <view class="address-detail">福建省厦门市翔安区xx路xx号</view>
        <view class="service">小型犬基础养护、基础检查</view>
        <view class="buttons">
          <view class="btn-reject">拒绝</view>
          <view class="btn-accept">接受</view>
        </view>
      </view>
    </view>
  </view>
</template>

<script setup>
import { ref } from 'vue'

const tabs = ref(['收到订单', '待完成', '已完成'])
const currentTab = ref('收到订单')
</script>

<style lang="scss" scoped>
.page {
  background: #F4F5F9;
  min-height: 100vh;
}

.tabs {
  display: flex;
  background: #FFFFFF;
  border-bottom: 1rpx solid #E5E5E5;
  position: sticky;
  top: 0;
  z-index: 20;
}

.tab-item {
  flex: 1;
  text-align: center;
  padding: 20rpx 0;
  font-size: 32rpx;
  color: #999999;
  position: relative;
  
  &.active {
    color: #B2D76E;
    font-weight: bold;
    
    &::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 60rpx;
      height: 4rpx;
      background: #B2D76E;
    }
  }
}

.order-list {
  padding: 20rpx 30rpx;
}

.order-card {
  background: #FFFFFF;
  border-radius: 16rpx;
  margin-bottom: 20rpx;
  overflow: hidden;
}

.card-header {
  background: linear-gradient(135deg, #B2D76E 0%, #FFFFFF 100%);
  padding: 20rpx 30rpx;
  display: flex;
  align-items: center;
  gap: 20rpx;
}

.order-type {
  font-size: 36rpx;
  color: #335700;
  font-weight: bold;
}

.time {
  flex: 1;
  font-size: 24rpx;
  color: #335700;
}

.price {
  font-size: 32rpx;
  font-weight: bold;
  color: #D63A3A;
}

.address-main {
  font-size: 30rpx;
  color: #333333;
  font-weight: bold;
  padding: 20rpx 30rpx 8rpx;
}

.address-detail {
  font-size: 24rpx;
  color: #999999;
  padding: 0 30rpx 8rpx;
}

.service {
  font-size: 26rpx;
  color: #000000;
  padding: 0 30rpx 20rpx;
}

.buttons {
  display: flex;
  gap: 20rpx;
  padding: 0 30rpx 30rpx;
}

.btn-reject, .btn-accept {
  flex: 1;
  text-align: center;
  padding: 18rpx 0;
  border-radius: 16rpx;
  font-size: 28rpx;
  color: #000000;
}

.btn-reject {
  background: #FFFFFF;
  border: 1rpx solid #E5E5E5;
}

.btn-accept {
  background: #B2D76E;
}
</style>
