<template>
  <view class="progress-class">
    <van-collapse accordion :value="activeName" @change="onChange">
      <van-collapse-item name="1">
        <view slot="title" class="coll-class">
          <van-image
              style="display: inline-flex;"
              round
              fit="cover"
              width="1.5rem"
              height="1.5rem"
              src="https://img.yzcdn.cn/vant/cat.jpeg"
          />
          &nbsp;
          <view>标题1</view>
        </view>
        <van-steps
            class="title-class"
            :steps="steps"
            :active="active"
            direction="vertical"
            active-color="#bf9f6f"
        />
      </van-collapse-item>
      <van-collapse-item name="2">
        <view slot="title" class="coll-class">
          <van-image
              style="display: inline-flex;"
              round
              fit="cover"
              width="1.5rem"
              height="1.5rem"
              src="https://img.yzcdn.cn/vant/cat.jpeg"
          />
          &nbsp;
          <view>标题2</view>
        </view>
        <van-steps
            class="title-class"
            :steps="steps"
            :active="active"
            direction="vertical"
            active-color="#bf9f6f"
        />
      </van-collapse-item>
    </van-collapse>
  </view>
  <van-action-sheet :show="show" title="邮寄到以下地址" @close="onClose">
    <view class="site-class">
      <view>
        <van-cell-group :border="false">
          <view class="cell-class">
            <van-cell @click="goAddSite" title="北京市朝阳区鸿博家园二期D区14号楼3单元2301" label="胡智彬 15166089918">
              <van-icon slot="right-icon" name="arrow"/>
            </van-cell>
          </view>
        </van-cell-group>
      </view>
    </view>
    <view style="text-align: center;padding: 10rpx 20rpx">
      <van-button type="default" color="#d6ba8c" :round="true" block>确认加入</van-button>
    </view>
  </van-action-sheet>
  <van-goods-action>
    <van-goods-action-button text="立即加入" color="#d6ba8c" @click="onClose"/>
  </van-goods-action>
</template>
<script setup>
import {ref} from 'vue';

const active = ref(1);
const show = ref(false);
const activeName = ref('1');
const onChange = (event) => {
  activeName.value = event.detail
};
const showChoo = () => {
  uni.chooseAddress({
    success: (res) => {
      console.log(res);
    },
    fail: (err) => {

    }
  })
}
const goAddSite = () => {
  uni.navigateTo({
    url: '/pages/site/index'
  });
}
const onClose = () => {
  show.value = !show.value
}
const steps = ref([
  {
    text: '等待收货',
    desc: '2024-03-27 13:42',
    inactiveIcon: 'description-o',
    activeIcon: 'todo-list-o',
  },
  {
    text: '正在进行',
    desc: '2024-03-27 13:42',
    inactiveIcon: 'description-o',
    activeIcon: 'todo-list-o',
  },
  {
    text: '已发货',
    desc: '2024-03-27 13:42',
    inactiveIcon: 'description-o',
    activeIcon: 'todo-list-o',
  },
  {
    text: '已结束',
    desc: '2024-03-27 13:42',
    inactiveIcon: 'description-o',
    activeIcon: 'todo-list-o',
  }
])
</script>
<style lang="scss">
.van-button--danger {
  font-size: 30rpx !important;
}

.van-button--default {
  font-size: 30rpx !important;
}

.site-class {
  padding: 10upx 10upx;

  .cell-class {
    .van-cell, .van-cell__label {
      font-size: 30rpx !important;
    }
  }
}

.progress-class {
  padding: 20upx 30upx;

  .van-cell {
    //padding-left: 0;
  }

  .van-collapse-item__content {
    padding: 10upx 30upx !important;
  }

  .coll-class {
    font-size: 35upx !important;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-items: center;
  }

  .van-hairline {
    padding: 10upx !important;
  }

  .van-step__icon {
    font-size: 30upx !important;
  }

  .van-step__title {
    font-size: 26upx !important;

    & > view:nth-child(1) {
      font-weight: bolder !important;
      margin-bottom: 10upx;
    }
  }
}


</style>