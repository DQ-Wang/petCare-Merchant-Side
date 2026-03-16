<template>
  <view class="section-card">
    <view
      v-for="item in functionList"
      :key="item.key"
      class="menu-item"
      @click="$emit('select-menu', item)"
    >
      <view class="left-area">
        <view class="menu-icon-wrap">
          <view class="menu-icon-mask" :style="getIconMaskStyle(item.iconPath)"></view>
        </view>
        <text class="menu-label">{{ item.text }}</text>
      </view>
      <text class="arrow">></text>
    </view>
  </view>
</template>

<script setup>
defineProps({
  functionList: {
    type: Array,
    default: () => []
  }
})

defineEmits(['select-menu'])

const getIconMaskStyle = (iconPath) => ({
  maskImage: `url(${iconPath})`,
  WebkitMaskImage: `url(${iconPath})`
})
</script>

<style scoped>
.section-card {
  background: #ffffff;
  border-radius: 32rpx;
  padding: 16rpx 40rpx;
}

.menu-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20rpx 0;
}

.left-area {
  display: flex;
  align-items: center;
  gap: 20rpx;
}

.menu-icon-wrap {
  width: 72rpx;
  height: 72rpx;
  display: flex;
  align-items: center;
  justify-content: center;
}

.menu-icon-mask {
  width: 42rpx;
  height: 42rpx;
  background-color: #4d4d4d;
  mask-repeat: no-repeat;
  mask-position: center;
  mask-size: contain;
  -webkit-mask-repeat: no-repeat;
  -webkit-mask-position: center;
  -webkit-mask-size: contain;
}

.menu-label {
  font-size: 28rpx;
  color: #333333;
}

.arrow {
  color: #b2d76e;
  font-size: 28rpx;
  font-weight: 700;
}
</style>
