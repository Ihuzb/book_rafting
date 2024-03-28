<template>
  <view class="site-class">
    <view>
      <van-cell-group>
        <van-field
            :value="siteInfo.username"
            clearable
            label="姓名"
            placeholder="请输入姓名"
            title-width="3em"
        />
        <van-field
            :value="siteInfo.username"
            clearable
            label="电话"
            placeholder="请输入电话"
            type="number"
            title-width="3em"
        />
        <van-field
            :value="siteInfo.username"
            clearable
            label="地址"
            placeholder="请输入所在地区"
            title-width="3em"
        />
        <van-field
            :value="siteInfo.password"
            type="textarea"
            label=" "
            placeholder="详细地址，街道、小区、单元、门牌号"
            title-width="3em"
        />
      </van-cell-group>
      <view class="tip-class">
        <view class="hang-class" style="margin-bottom: 10rpx">
          <view>
            <van-icon name="warning" style="color: #bf9f6f"/>
          </view>
          <view style="margin-left: 20rpx">订单取件、订单寄件会使用设置的地址，请确认信息正确</view>
        </view>
        <view class="hang-class">
          <view>
            <van-icon name="warning" style="color: #bf9f6f"/>
          </view>
          <view style="margin-left: 20rpx">不会向您的手机号发送短信通知等信息</view>
        </view>
      </view>
    </view>
    <van-goods-action>
      <van-goods-action-button color="#d6ba8c">
        保存
      </van-goods-action-button>
    </van-goods-action>
  </view>
</template>
<script setup>
import {ref} from 'vue'

const siteInfo = ref({});
</script>
<style lang="scss">
.site-class {
  padding: 20rpx 30rpx;

  .van-field__control--textarea {
    height: 100rpx !important;
    font-size: 30rpx !important;
  }

  .van-cell {
    padding-left: 0;
    padding-right: 0;
    font-size: 30rpx;
  }

  .tip-class {
    margin-top: 30rpx;
    background: #ede7cd;
    color: #bf9f6f;
    padding: 20rpx;
    font-size: 25rpx;

    .hang-class {
      display: flex;
      flex-direction: row;
      flex-wrap: nowrap;
      align-items: flex-start;
      justify-content: flex-start;
    }
  }

  .van-button--danger {
    font-size: 30rpx !important;
  }
}
</style>