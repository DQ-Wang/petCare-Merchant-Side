<template>
  <scroll-view class="workbench-page" scroll-y>
    <view class="top-gradient"></view>
    <view class="content-wrap">
      <UserInfoSection :user-info="userInfo" />
      <IncomeStatsSection :income-data="incomeData" />
      <OrderManageSection
        :order-entrance="orderEntrance"
        @all-orders="handleAllOrders"
        @select-order="handleOrderSelect"
      />
      <FunctionMenuSection :function-list="functionList" @select-menu="handleMenuSelect" />
    </view>
  </scroll-view>
</template>

<script setup>
import { reactive } from 'vue'
import UserInfoSection from './components/UserInfoSection.vue'
import IncomeStatsSection from './components/IncomeStatsSection.vue'
import OrderManageSection from './components/OrderManageSection.vue'
import FunctionMenuSection from './components/FunctionMenuSection.vue'

const userInfo = reactive({
  nickname: '授权昵称',
  platform: '平台',
  avatarText: '汪汪喵'
})

const incomeData = reactive({
  totalIncome: '0.00',
  monthlyIncome: '0.00',
  withdrawable: '0.00'
})

const orderEntrance = reactive([
  { key: 'hall', text: '任务大厅', iconPath: '/static/workbench/order-manage/task-hall.png', type: 'hall' },
  { key: 'accepted', text: '已接单', iconPath: '/static/workbench/order-manage/accepted.png', type: 'accepted' },
  { key: 'served', text: '已服务', iconPath: '/static/workbench/order-manage/served.png', type: 'served' },
  { key: 'done', text: '已完成', iconPath: '/static/workbench/order-manage/completed.png', type: 'done' }
])

const functionList = reactive([
  { key: 'qrcode', text: '我的二维码', iconPath: '/static/workbench/function-menu/qrcode.png' },
  { key: 'withdraw', text: '申请提现', iconPath: '/static/workbench/function-menu/withdraw.png' },
  { key: 'withdraw-record', text: '提现记录', iconPath: '/static/workbench/function-menu/withdraw-record.png' },
  { key: 'withdraw-account', text: '提现账号', iconPath: '/static/workbench/function-menu/withdraw-account.png' },
  { key: 'urgent-rent', text: '紧急求租', iconPath: '/static/workbench/function-menu/urgent-rent.png' },
  { key: 'scan-check', text: '扫码核销', iconPath: '/static/workbench/function-menu/scan-check.png' },
  { key: 'bind-notice', text: '绑定公众号通知', iconPath: '/static/workbench/function-menu/bind-notice.png' }
])

const handleAllOrders = () => {
  uni.switchTab({
    url: '/pages/orders/orders'
  })
}

const handleOrderSelect = (item) => {
  if (item.type === 'hall') {
    uni.switchTab({
      url: '/pages/receive-orders/receive-orders'
    })
    return
  }

  uni.switchTab({
    url: '/pages/orders/orders'
  })
}

const handleMenuSelect = (item) => {
  uni.showToast({
    title: item.text,
    icon: 'none'
  })
}
</script>

<style lang="scss" scoped>
@import "../../petcareui/pet-global.css";

.workbench-page {
  min-height: 100vh;
  background: #f5f7f9;
}

.top-gradient {
  position: relative;
  height: 220rpx;
  background: linear-gradient(to bottom, #ddebc8, #f5f7f9);
  overflow: hidden;
}

.content-wrap {
  margin-top: -20rpx;
  padding: 0 0 40rpx 0;
  box-sizing: border-box;
}

.content-wrap > view {
  margin: 0 30rpx 30rpx;
}

.content-wrap > view:first-child {
  margin-bottom: -12rpx;
}
</style>
