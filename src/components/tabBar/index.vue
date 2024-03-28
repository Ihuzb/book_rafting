<template>
  <van-tabbar :active="active" @change="onChange"   active-color="#d6ba8c"
              inactive-color="#000">
    <van-tabbar-item icon="list-switch" name="home">首页</van-tabbar-item>
    <van-tabbar-item name="search" icon="manager-o" url="/pages/user/index">我的</van-tabbar-item>
  </van-tabbar>
</template>
<script setup>
import {ref} from "vue";

const active = ref('home');
const icon = {
  home: {
    normal: '/static/image/book-apple.svg',
    active: '/static/image/book-apple.svg',
  }
}
const onChange = (event) => {
  active.value = event.detail
}
</script>
<style scoped>

</style>