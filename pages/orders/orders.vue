<template>
  <scroll-view class="order-detail-page" scroll-y>
    <AddressSection :address="orderData.address" @navigate="navigateToAddress" />
    <OrderInfoSection :order-info="orderData" />
    <RemarkSection :remark="orderData.remark" />
  </scroll-view>
</template>

<script setup>
import { reactive } from 'vue'
import { onLoad } from '@dcloudio/uni-app'
import AddressSection from './components/AddressSection.vue'
import OrderInfoSection from './components/OrderInfoSection.vue'
import RemarkSection from './components/RemarkSection.vue'

const orderData = reactive({
  address: '厦门大学（翔安校区）国光公寓（翔安区香山街道东园村厦门大学翔安校区）国光15',
  avatar: '/static/orders/customer-avatar.png',
  userName: '李女士',
  phone: '123456789',
  serviceTime: '7.13（本周日）13:00',
  petType: '猫',
  packageName: '基础护理',
  baseService: '全程录像、检查环境隐患',
  extraService: '宠物健康基础检查',
  totalPrice: 55,
  remark: '师傅你到了小区门口后在门卫那里登记一下就可以进来了！我在国光15—999宿舍。'
})

onLoad((options) => {
  if (options.address) {
    orderData.address = decodeURIComponent(options.address)
  }
})

const navigateToAddress = () => {
  uni.showToast({
    title: '查看地址详情',
    icon: 'none'
  })
}
</script>

<style lang="scss" scoped>
@import "../../petcareui/pet-global.css";

.order-detail-page {
  min-height: 100vh;
  background: #f4f5f9;
  padding: 20rpx 30rpx;
  box-sizing: border-box;
}

.order-detail-page :deep(.section-card) {
  margin-bottom: 20rpx;
}

.order-detail-page :deep(.section-title) {
  position: relative;
  padding-left: 20rpx;
}

.order-detail-page :deep(.section-title::before) {
  content: '';
  position: absolute;
  left: 0;
  top: 8rpx;
  width: 8rpx;
  height: 32rpx;
  border-radius: 8rpx;
  background: #b2d76e;
}
</style>
