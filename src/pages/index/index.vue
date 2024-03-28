<template>
  <view>
    <view class="content waterfall">
      <template v-for="(item, index) in toList()">
        <BookCard class="item" :cover="item.url" :name="item.name"/>
      </template>
    </view>
    <view>
      <TabBar/>
    </view>
  </view>
</template>
<script setup>
import BookCard from '/src/components/bookCard/bookCard.vue'
import TabBar from '/src/components/tabBar/index.vue'

const coverList = [
  {
    name: '小王子1',
    url: 'https://img12.360buyimg.com/n0/jfs/t1/158109/2/13090/30774/6051e9c8Efac46f9a/990628894f6b6f7b.jpg'
  },
  {name: '活着2', url: 'http://t13.baidu.com/it/u=2978882583,4288525078&fm=224&app=112&f=JPEG?w=360&h=499'},
  {
    name: '小王子3',
    url: 'https://img12.360buyimg.com/n0/jfs/t1/158109/2/13090/30774/6051e9c8Efac46f9a/990628894f6b6f7b.jpg'
  },
  {name: '活着4', url: 'http://t13.baidu.com/it/u=2978882583,4288525078&fm=224&app=112&f=JPEG?w=360&h=499'},
  {
    name: '小王子5',
    url: 'https://img12.360buyimg.com/n0/jfs/t1/158109/2/13090/30774/6051e9c8Efac46f9a/990628894f6b6f7b.jpg'
  },
  {name: '活着6', url: 'http://t13.baidu.com/it/u=2978882583,4288525078&fm=224&app=112&f=JPEG?w=360&h=499'},
  {name: '活着6', url: 'http://t13.baidu.com/it/u=2978882583,4288525078&fm=224&app=112&f=JPEG?w=360&h=499'},
]
const toList = () => {
  let left = coverList.filter((item, index) => index % 2 == 0);
  let right = coverList.filter((item, index) => index % 2 == 1);
  return left.concat(right);
}

</script>

<style lang="scss">
page {
  background: #fafafa;
}

.content {
  //height: 100vh;
  overflow-y: auto;
  padding: 10upx;
  box-sizing: border-box;
}

.waterfall {
  column-count: 2; /* 根据需要设置列数 */
  column-gap: 10upx; /* 列间距 */
}

.item {
  break-inside: avoid; /* 避免元素跨列 */
  margin-bottom: 10upx; /* 行间距 */
  display: block;
}
</style>
