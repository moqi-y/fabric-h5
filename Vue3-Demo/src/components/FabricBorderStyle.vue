<!--
 * @Author: yuanzhen
 * @Date: 2023-08-16 20:12:26
 * @LastEditTime: 2023-08-17 10:49:00
 * @FilePath: \fabric-h5\Vue3-Demo\src\components\FabricBorderStyle.vue
 * @Description: 
-->
<template>
    <div>
        <h1>Fabric-Vue3 边框样式</h1>
        <canvas id="canvas2" width="900" height="600"></canvas>
    </div>
</template>

<script setup lang="ts">
import { onMounted } from 'vue';
import { fabric } from 'fabric'
onMounted(() => {
    // // 初始化画布
    var canvas = new fabric.Canvas('canvas2');
    /**
     * 隐藏边框线效果
     */
    fabric.Image.fromURL('https://img1.imgtp.com/2023/08/16/XXozyfMm.png', function (oImg) {
        oImg.scale(0.6)  //将图片缩小0.6倍
        oImg.hasBorders = false;  //隐藏边框线
        canvas.add(oImg);  //将图片添加到画布上
    });


    /**
     * 隐藏控制点效果
     */
    fabric.Image.fromURL('https://img1.imgtp.com/2023/08/17/XXSIrLpI.png', function (oImg) {
        oImg.scale(0.4)  //将图片缩小0.4倍
        oImg.hasControls = false;  //隐藏控制点
        canvas.add(oImg);  //将图片添加到画布上
    });

    /**
     * 自定义边框颜色
     */
    fabric.Image.fromURL('https://img1.imgtp.com/2023/08/17/9lMZxoA6.png', function (oImg) {
        oImg.set({
            transparentCorners: false, //控制点是否实心填充
            cornerColor: 'blue',    //控制点颜色
            cornerStrokeColor: 'red', //控制点边框颜色
            borderColor: 'green',   //边框颜色
            cornerSize: 12,     //控制点大小
            padding: 10,   //边框与图片的距离
            cornerStyle: 'circle',  //控制点样式
            borderDashArray: [3, 3]  //边框虚线
        });
        canvas.add(oImg);  //将图片添加到画布上
    });

});

</script>

<style scoped>
#canvas2 {
    border: 6px dashed #ccc;
}
</style>
