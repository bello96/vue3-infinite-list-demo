<script setup>
import InfiniteList from 'vue3-infinite-list';

defineProps({
  dataList: Array
})

// 通过这个函数可以动态设置元素宽高.
const getItemSize = (i) => {
  switch (i % 4) {
    case 1:
      return 80;
    case 2:
      return 50;
    case 3:
      return 100;
    default:
      return 200;
  }
};


</script>

<template>
  <InfiniteList :data="dataList" :scrollToIndex="106" :width="'100%'" :height="500" :itemSize="getItemSize"
    v-slot="{ item, index }">
    <div :class="index % 2 ? 'odd' : 'even'">{{ index + 1 }} : {{ item }}</div>
  </InfiniteList>

</template>

<style scoped>
.odd {
  background-color: pink;
  height: 100%;
}

.even {
  background-color: rgb(207, 115, 115);
  height: 100%;
}
</style>
