<template>
  <view class="container">
    <view class="card welcome-card">
      <text class="section-title">你好，开始今天的口语练习吧</text>
      <text class="desc">本小程序聚焦“英语口语”，但所有界面和提示均为中文，帮助你更顺畅地学习。</text>
      <view class="primary-btn" @click="goPractice">立即开始练习</view>
    </view>

    <view class="card">
      <text class="section-title">学习建议</text>
      <view class="tip-item" v-for="(tip, index) in tips" :key="index">
        <text>{{ index + 1 }}. {{ tip }}</text>
      </view>
    </view>
  </view>
</template>

<script setup>
const tips = [
  '先听后读：先播放示例，再跟读模仿。',
  '短句高频重复：每天至少重复 5 次核心句。',
  '结合情景：把句子带入真实场景中练习。'
]

const goPractice = () => {
  uni.navigateTo({ url: '/pages/practice/index' })
}
</script>

<style scoped>
.container {
  padding: 24rpx;
  display: flex;
  flex-direction: column;
  gap: 20rpx;
}

.welcome-card .desc {
  color: #4b5563;
  line-height: 1.7;
}

.tip-item {
  margin-bottom: 14rpx;
  color: #374151;
}
</style>
