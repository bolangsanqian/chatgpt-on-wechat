<template>
  <view class="container">
    <view class="card" v-for="scenario in scenarioDialogs" :key="scenario.id">
      <text class="section-title">{{ scenario.title }}</text>
      <text class="goal">学习目标：{{ scenario.chineseGoal }}</text>
      <view class="dialog-line" v-for="(line, index) in scenario.lines" :key="index">
        <text>{{ line }}</text>
      </view>
      <view class="primary-btn" @click="startScenario(scenario.title)">开始该场景练习</view>
    </view>
  </view>
</template>

<script setup>
import { scenarioDialogs } from '@/common/mock.js'

const startScenario = (title) => {
  uni.showModal({
    title: '开始练习',
    content: `你已进入“${title}”场景。接下来请用中文提示进行英语口语表达。`,
    showCancel: false,
    confirmText: '我知道了'
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

.goal {
  display: block;
  margin-bottom: 12rpx;
  color: #334155;
}

.dialog-line {
  padding: 10rpx 0;
  border-bottom: 1rpx dashed #dbeafe;
  color: #475569;
}

.dialog-line:last-child {
  border-bottom: none;
}
</style>
