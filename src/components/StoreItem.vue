<template>
    <div class="store-item store-item-box">
        <div v-if="!isHot" class="price">1500 Р</div>
        <div v-if="isHot" class="price is-hot-price">1500 Р</div>
        
        <div v-if="!isHot"
             class="div1">
            <img src="../assets/photo-sample-1.png"
                 alt=""
                 class="div-img">
        </div>
        <div v-if="!isHot"
             class="div2">
            <img src="../assets/photo-sample-2.png"
                 alt=""
                 class="div-img">
        </div>
        <div v-if="!isHot"
             class="div3">
            <img src="../assets/photo-sample-3.png"
                 alt=""
                 class="div-img">
        </div>

        <div v-if="isHot"
             class="div5">
            <img src="../assets/photo-sample-3.png"
                 alt=""
                 class="div-img">
        </div>
        <div v-if="isHot"
             class="div5">
            <img src="../assets/fire-layer.png"
                 alt=""
                 class="div-img">
        </div>
        
        <div class="div4">
            <img class="store-item__user-pic" src="../assets/user-avatar-1.png" 
                 alt="">
            <img class="store-item__user-pic-ellipse" src="../assets/Ellipse.svg"
                 alt="">
            <img class="store-item__user-pic-leaf" src="../assets/leaf-icon.svg"
                 alt="">
            
            <span class="store-item__master-name">Дмитрий Останинкинов</span>
            
        </div>
    </div>
</template>
<script lang="ts">
    export default {
        name: 'StoreItem',
        props: ['isHot'],
    }
</script>

<style src="./HelloWorld.less"
       scoped
       lang="less"></style>