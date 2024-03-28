<template>
  <view class="site-class">
    <view>
      <van-cell-group :border="false">
        <view class="cell-class">
          <view>
            <van-icon name="checked" color="#bf9f6f"/>
          </view>
          <view style="flex: 1">
            <van-cell title="北京市朝阳区鸿博家园二期D区14号楼3单元2301" label="胡智彬 15166089918">
              <van-icon slot="right-icon" name="edit" @click="goAddSite"/>
            </van-cell>
          </view>
        </view>
        <view class="cell-class">
          <van-cell title="北京市朝阳区鸿博家园二期D区14号楼3单元2301" label="胡智彬 15166089918">
            <van-icon slot="right-icon" name="edit"/>
          </van-cell>
        </view>
      </van-cell-group>
    </view>
    <van-goods-action>
      <van-goods-action-button color="#d6ba8c" url="/pages/add-site/index">
        <van-icon name="plus"/>
        添加新地址
      </van-goods-action-button>
    </van-goods-action>
  </view>
</template>
<script setup>
const goAddSite = () => {
  uni.navigateTo({
    url: '/pages/add-site/index'
  });
}
</script>
<style lang="scss">

.site-class {
  padding: 20upx 30upx;

  .van-button--danger {
    font-size: 30rpx !important;
  }

  .cell-class {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-items: center;

    .van-cell, .van-cell__label {
      font-size: 30rpx !important;
    }
  }
}
</style>