<template>
    <view class="Header">
       <text class="text">{{header}}</text> 
    </view>
</template>
<script>
export default {
    props: ['header']
}
</script>
<style>
    .Header{
        height: 60px;
    }
    .text{
        text-align: center;
        color: #fff;
        font-size: 25px;
        margin-top: 20;
    }
</style>