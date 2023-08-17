<!--
 * @Author: yuanzhen
 * @Date: 2023-08-16 20:12:26
 * @LastEditTime: 2023-08-17 10:12:39
 * @FilePath: \fabric-h5\Vue3-Demo\src\components\HelloFabric.vue
 * @Description: 
-->
<template>
  <div>
    <h1>Fabric-Vue3 初体验</h1>
    <canvas id="canvas1" width="900" height="600"></canvas>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';
import { fabric } from 'fabric'
onMounted(() => {
  // // 初始化画布
  var canvas = new fabric.Canvas('canvas1');
  fabric.Image.fromURL('https://img1.imgtp.com/2023/08/16/XXozyfMm.png', function (oImg) {
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
