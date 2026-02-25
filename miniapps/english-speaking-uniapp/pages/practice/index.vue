<template>
  <view class="container">
    <view class="card">
      <text class="section-title">每日练习句</text>
      <view class="sentence-card" v-for="item in dailySentences" :key="item.id">
        <text class="english">{{ item.english }}</text>
        <text class="chinese">中文：{{ item.chinese }}</text>
        <text class="tip">练习提示：{{ item.tip }}</text>
      </view>
    </view>

    <view class="card">
      <text class="section-title">模拟口语互动</text>
      <text class="desc">请输入你想练习的句子主题，我会用中文给你练习建议。</text>
      <input class="input" v-model="topic" placeholder="例如：自我介绍、问路、面试" />
      <view class="primary-btn" @click="generateFeedback">生成中文建议</view>
      <view class="feedback" v-if="feedback">
        <text>{{ feedback }}</text>
      </view>
    </view>
  </view>
</template>

<script setup>
import { ref } from 'vue'
import { dailySentences } from '@/common/mock.js'

const topic = ref('')
const feedback = ref('')

const generateFeedback = () => {
  if (!topic.value) {
    uni.showToast({ title: '请先输入练习主题', icon: 'none' })
    return
  }
  feedback.value = `你选择了“${topic.value}”。建议你先准备 3 句基础表达，再进行 2 轮问答模拟，最后录音复盘发音与语速。`
}
</script>

<style scoped>
.container {
  padding: 24rpx;
  display: flex;
  flex-direction: column;
  gap: 20rpx;
}

.sentence-card {
  padding: 16rpx;
  border-radius: 16rpx;
  background: #f8fafc;
  margin-bottom: 16rpx;
}

.english {
  font-size: 30rpx;
  font-weight: 600;
}

.chinese,
.tip,
.desc {
  display: block;
  margin-top: 8rpx;
  color: #475569;
}

.input {
  margin-top: 18rpx;
  background: #f8fafc;
  border: 2rpx solid #e2e8f0;
  border-radius: 12rpx;
  padding: 16rpx;
}

.feedback {
  margin-top: 20rpx;
  padding: 16rpx;
  border-radius: 12rpx;
  background: #eff6ff;
  color: #1d4ed8;
  line-height: 1.7;
}
</style>
