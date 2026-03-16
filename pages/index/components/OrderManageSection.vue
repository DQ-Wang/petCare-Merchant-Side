<template>
  <view class="section-card">
    <view class="section-head" @click="$emit('all-orders')">
      <text class="section-title">订单管理</text>
      <view class="head-action">
        <text class="all-text">全部订单</text>
        <text class="arrow">></text>
      </view>
    </view>

    <view class="order-grid">
      <view
        v-for="item in orderEntrance"
        :key="item.key"
        class="order-item"
        @click="$emit('select-order', item)"
      >
        <view class="icon-wrap">
          <view class="icon-mask" :style="getIconMaskStyle(item.iconPath)"></view>
        </view>
        <text class="item-text">{{ item.text }}</text>
      </view>
    </view>
  </view>
</template>

<script setup>
defineProps({
  orderEntrance: {
    type: Array,
    default: () => []
  }
})

defineEmits(['all-orders', 'select-order'])

const getIconMaskStyle = (iconPath) => ({
  maskImage: `url(${iconPath})`,
  WebkitMaskImage: `url(${iconPath})`
})
</script>

<style scoped>
.section-card {
  background: #ffffff;
  border-radius: 32rpx;
  padding: 40rpx;
}

.section-head {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.section-title {
  font-size: 32rpx;
  color: #333333;
  font-weight: 700;
}

.head-action {
  display: flex;
  align-items: center;
  gap: 10rpx;
}

.all-text {
  font-size: 24rpx;
  color: #999999;
}

.arrow {
  color: #b2d76e;
  font-size: 28rpx;
  font-weight: 700;
}

.order-grid {
  display: flex;
  justify-content: space-between;
  margin-top: 30rpx;
}

.order-item {
  width: 25%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4rpx;
}

.icon-wrap {
  width: 78rpx;
  height: 78rpx;
  display: flex;
  align-items: center;
  justify-content: center;
}

.icon-mask {
  width: 40rpx;
  height: 40rpx;
  background-color: #b2d76e;
  mask-repeat: no-repeat;
  mask-position: center;
  mask-size: contain;
  -webkit-mask-repeat: no-repeat;
  -webkit-mask-position: center;
  -webkit-mask-size: contain;
}

.item-text {
  font-size: 24rpx;
  color: #333333;
}
</style>
