<template>
  <view>
    <view class="image-class">
      <image style="width: 30%;" mode="widthFix" class="show-class" @click="setShow"
             src="http://t13.baidu.com/it/u=2978882583,4288525078&fm=224&app=112&f=JPEG?w=360&h=499"></image>
      <image style="width: 100%;height: 100%;" mode="aspectFill" class="background-class"
             src="http://t13.baidu.com/it/u=2978882583,4288525078&fm=224&app=112&f=JPEG?w=360&h=499"></image>
      <van-popup :show="show" @click-overlay="setShow">
        <image mode="widthFix"
               src="http://t13.baidu.com/it/u=2978882583,4288525078&fm=224&app=112&f=JPEG?w=360&h=499"></image>
      </van-popup>
    </view>
    <view class="content-class">
      <view class="user-class">
        <van-row>
          <van-col span="11">
            <view style="overflow: hidden;white-space: nowrap;text-overflow: ellipsis;">
              爱吃馒头不吃辣，明安，爱吃馒头不吃辣，明安，爱吃馒头不吃辣，明安，爱吃馒头不吃辣，明安，
            </view>
          </van-col>
          <van-col span="11">等100人看过此书</van-col>
          <van-col span="2">
            <van-icon name="arrow"/>
          </van-col>
        </van-row>
      </view>
      <van-divider customStyle="margin:0;"/>
      <view class="text-class">
        活着
      </view>

      <view class="info-class">
        <view>
          <view style="margin-right: 0.3rem;" class="info-title">作&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;者</view>
          :&nbsp;&nbsp;余华
        </view>
        <view>
          <view style="margin-right: 0.3rem;" class="info-title">出&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;版</view>
          :&nbsp;&nbsp;2020-09
        </view>
        <view>
          <view class="info-title">出&nbsp;版&nbsp;社</view>
          :&nbsp;&nbsp;人民文学出版社
        </view>
      </view>
      <view class="rate-class">
        <view class="douban-class">豆瓣评分 9.9</view>
        <view class="rate">
          <van-rate color="#d6ba8c" size="15" value="3"/>
        </view>
      </view>
      <view class="text-class">
        简介
      </view>
      <view class="info-text-class">
        这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一，本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错
        这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一，本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错
        这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一，本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错
        这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一，本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错
        这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一，本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错
        这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一，本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的这是一本好书很不错的的
        3335555
      </view>
    </view>
    <van-goods-action>
      <van-goods-action-icon textClass="text-class-aaa" style="font-size: 2em" icon="list-switch" text="首页"/>
<!--      <van-goods-action-button text="当前进度" type="warning"  color="#bf9f6f" url="/pages/progress-list/index" />-->
      <van-goods-action-button text="立即加入" color="#d6ba8c" url="/pages/progress-list/index"/>
    </van-goods-action>
  </view>
</template>
<script setup>
import {ref} from 'vue';

const show = ref(false);
const setShow = () => {
  show.value = !show.value
}
</script>
<style scoped lang="scss">
.image-class {
  width: 100vw;
  position: relative;
  text-align: center;
  height: 400upx;
  overflow: hidden;

  .background-class {
    filter: blur(10px);
  }

  .show-class {
    z-index: 9;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
  }
}

.content-class {
  padding: 20upx 30upx;
  padding-bottom: 150upx;

  .text-class {
    font-size: 40upx;
    margin-top: 30upx;
  }

  .user-class {
    text-align: center;
    margin-bottom: 20upx;
    font-size: 25upx;
  }

  .info-class {
    font-size: 28upx;
    margin-top: 20upx;

    .info-title {
      color: #999999;
      margin-right: 0.2rem;
      display: inline-block;
    }
  }

  .rate-class {
    font-size: 28upx;
    color: #d6ba8c;
    margin-top: 30upx;
    padding: 15upx 15upx;
    background: #fafafa;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;

    & > view {
      display: inline-block;
    }
  }

  .info-text-class {
    font-size: 30upx;
    margin-top: 20upx;
  }
}

</style>