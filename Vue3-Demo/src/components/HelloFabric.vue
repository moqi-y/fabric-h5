<!--
 * @Author: yuanzhen
 * @Date: 2023-08-16 20:12:26
 * @LastEditTime: 2023-10-10 09:43:15
 * @FilePath: \fabric-h5\Vue3-Demo\src\components\HelloFabric.vue
 * @Description: 
-->
<template>
  <div>
    <h1>Fabric-Vue3 初体验</h1>
    <canvas id="canvas1" width="1200" height="600"></canvas>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';
import { fabric } from 'fabric'
onMounted(() => {
  // // 初始化画布
  var canvas = new fabric.Canvas('canvas1');
  fabric.Image.fromURL('https://tucdn.wpon.cn/2023/10/10/91b787da57268.jpg', function (oImg) {
    oImg.scale(0.6)  //将图片缩小0.6倍
    canvas.add(oImg);  //将图片添加到画布上
  });
});

</script>

<style scoped>
#canvas1 {
  border: 6px dashed #ccc;
}
</style>
