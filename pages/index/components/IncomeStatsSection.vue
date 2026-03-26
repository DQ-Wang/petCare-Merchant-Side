<template>
  <view class="income-card">
    <view v-for="item in statsList" :key="item.label" class="income-item">
      <text class="amount">{{ item.value }}</text>
      <text class="label">{{ item.label }}</text>
    </view>
  </view>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  incomeData: {
    type: Object,
    default: () => ({})
  }
})

const statsList = computed(() => [
  { label: '总收入', value: props.incomeData.totalIncome },
  { label: '本月收入', value: props.incomeData.monthlyIncome },
  { label: '可提现', value: props.incomeData.withdrawable }
])
</script>

<style scoped>
.income-card {
  background: #b2d76e;
  border-radius: 32rpx;
  padding: 40rpx 0;
  display: flex;
}

.income-item {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12rpx;
}

.amount {
  font-size: 42rpx;
  color: #000000;
  font-weight: 700;
}

.label {
  font-size: 24rpx;
  color: #335700;
  font-weight: 700;
}
</style>
