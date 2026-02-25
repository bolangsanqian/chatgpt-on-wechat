<template>
  <view class="app-root">
    <slot />
  </view>
</template>

<script>
export default {
  onLaunch() {
    console.log('英语口语练习小程序已启动')
  }
}
</script>

<style>
page {
  background: #f3f4f6;
  font-size: 28rpx;
  color: #111827;
}

.card {
  background: #ffffff;
  border-radius: 20rpx;
  padding: 28rpx;
  box-shadow: 0 8rpx 20rpx rgba(15, 23, 42, 0.06);
}

.section-title {
  font-size: 34rpx;
  font-weight: 700;
  margin-bottom: 20rpx;
}

.primary-btn {
  margin-top: 24rpx;
  background: #2563eb;
  color: #ffffff;
  border-radius: 9999rpx;
  text-align: center;
  padding: 18rpx 0;
  font-size: 30rpx;
}
</style>
