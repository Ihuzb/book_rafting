<script setup>
const props = defineProps({
  cover: String,
  name: String,
})
const navigateToPage = () => {
  uni.navigateTo({
    url: '/pages/info/index'
  });
}
</script>

<template>
  <view class="book-item" @click="navigateToPage">
    <view>
      <image style="width: 80%;" mode="widthFix" :src="cover"></image>
    </view>
    <view class="uni-body">
      <text>{{ name}}</text>
    </view>
  </view>
</template>

<style scoped lang="scss">
.book-item {
  text-align: center;
  padding: 30upx 40upx;
  background: white;

  .uni-body {
    margin-top: 30upx;
    font-size: 34upx;
    font-weight: bolder;
  }
}
</style>