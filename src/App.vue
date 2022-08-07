<script setup>
import HelloWorld from './components/HelloWorld.vue'
import { reactive } from 'vue';
const dataList = reactive([])
for (let i = 0; i < 1000; i++) {
  dataList.push(i)
}
</script>

<template>
  <div class="app">
    <HelloWorld :dataList="dataList" />
  </div>

</template>

<style scoped>
.app {
  width: 500px;
  height: 500px;
  border: 1px solid red;
}
</style>
