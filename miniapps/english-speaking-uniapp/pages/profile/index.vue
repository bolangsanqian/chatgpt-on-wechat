<template>
  <view class="container">
    <view class="card">
      <text class="section-title">学习中心</text>
      <view class="metric-row">
        <text>连续学习</text>
        <text class="metric-value">7 天</text>
      </view>
      <view class="metric-row">
        <text>今日完成</text>
        <text class="metric-value">3 / 3 任务</text>
      </view>
      <view class="metric-row">
        <text>累计练习时长</text>
        <text class="metric-value">126 分钟</text>
      </view>
    </view>

    <view class="card">
      <text class="section-title">中文学习提醒</text>
      <view class="primary-btn" @click="notify">开启每日中文提醒</view>
    </view>
  </view>
</template>

<script setup>
const notify = () => {
  uni.showToast({
    title: '已开启，每天 20:00 提醒你练习口语',
    icon: 'none'
  })
}
</script>

<style scoped>
.container {
  padding: 24rpx;
  display: flex;
  flex-direction: column;
  gap: 20rpx;
}

.metric-row {
  display: flex;
  justify-content: space-between;
  padding: 14rpx 0;
  border-bottom: 1rpx solid #e5e7eb;
}

.metric-row:last-child {
  border-bottom: none;
}

.metric-value {
  color: #2563eb;
  font-weight: 700;
}
</style>
